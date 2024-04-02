<script>
  import { onMount } from 'svelte';
  import { onAuthStateChanged, signOut } from 'firebase/auth';
  import toast from 'svelte-french-toast';
  import { fauth } from "../firebase";
  import { userStore } from "../stores/userStore";

  let headerBtn, headerNav, header, myModalEl;
  let me;

  onMount(() => {
    document.title = "WEBUInet | Home";

    const saveSettings = () => {
      return new Promise((resolve, reject) => {
        let x = setInterval(() => {
          if (userStore.loggedIn === true) {
            resolve();
            clearInterval(x);
          } else if (userStore.loggedIn === false) {
            reject();
            clearInterval(x);
          }
        }, 100);
      });
    };

    toast.promise(
      saveSettings(),
      {
        loading: 'Checking...',
        success: 'Signed In!',
        error: 'You are not signed In!',
      }
    );

    onAuthStateChanged(fauth, async (user) => {
      if (user) {
        userStore.set({...user, loggedIn: true});
        me = user;
      } else {
        me = false;
        console.log('User Not Logged In!');
        userStore.set({loggedIn: false});
      }
    });

    headerBtn = document.querySelector('.header__btn');
    headerNav = document.querySelector('.header__nav');
    header = document.querySelector('.header');
    myModalEl = document.getElementById('modal-wallet');

    headerBtn.addEventListener('click', toggleHeader);
    window.addEventListener('scroll', handleScroll);

    myModalEl.addEventListener('show.bs.modal', handleModalShow);
    myModalEl.addEventListener('hidden.bs.modal', handleModalHidden);

    // Initialize header state based on scroll position
    handleScroll();
  });

  function toggleHeader() {
    headerBtn.classList.toggle('header__btn--active');
    headerNav.classList.toggle('header__nav--active');

    if (window.scrollY === 0) {
      header.classList.toggle('header--active');
    }
  }

  function handleScroll() {
    if (window.scrollY > 0) {
      header.classList.add('header--active');
    } else {
      header.classList.remove('header--active');
    }
  }

  function handleModalShow(event) {
    if (window.innerWidth > 1200) {
      const scrollBarWidth = window.innerWidth - document.documentElement.clientWidth;
      header.style.paddingRight = `${scrollBarWidth}px`;
    }
  }

  function handleModalHidden(event) {
    if (window.innerWidth > 1200) {
      header.style.paddingRight = '';
    }
  }
</script>
<svelte:head>
  <link rel="stylesheet" href="/css/bootstrap.min.css">
	<link rel="stylesheet" href="/css/blueimp-gallery.min.css">
	<link rel="stylesheet" href="/css/splide.min.css">
	<link rel="stylesheet" href="/css/slimselect.css">
	<link rel="stylesheet" href="/css/main.css">
</svelte:head>

<!-- Your HTML structure goes here -->
<Toaster/>
<header class="header">
  <div class="container">
    <div class="row">
      <div class="col-12">
        <div class="header__content">
          <!-- btn -->
          <button class="header__btn" type="button" aria-label="header__nav">
            <span></span>
            <span></span>
            <span></span>
          </button>
          <!-- end btn -->

          <!-- logo -->
          <a href="/" class="header__logo">
            <img src="logo.svg"/>
          </a>
          <!-- end logo -->

          <!-- tagline -->
          <span class="header__tagline">WEBUINET</span>
          <!-- end tagline -->

          <!-- navigation -->
          <ul class="header__nav" id="header__nav">
            <!-- Navigation links -->
            <li><a href="/">Home</a></li>
 <li><a href="login">Login</a></li>
									<li><a href="register">Register</a></li>
									<li><a href="forgot">Forgot password</a></li>
									<li><a href="404">404 Page</a></li>
									<li><a href="privacy">Privacy policy</a></li>
            <li><a href="explore">Explore</a></li>
									<li><a href="profile">Profile</a></li>
									<li><a href="blogs">Blog</a></li>
									<li><a href="add">Add new game</a></li>
          </ul>
          <!-- end navigation -->

          <!-- wallet -->
          <button type="button" data-bs-toggle="modal" class="header__cta" data-bs-target="#modal-wallet">
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24">
              <path d="M19,7H18V6a3,3,0,0,0-3-3H5A3,3,0,0,0,2,6H2V18a3,3,0,0,0,3,3H19a3,3,0,0,0,3-3V10A3,3,0,0,0,19,7ZM5,5H15a1,1,0,0,1,1,1V7H5A1,1,0,0,1,5,5ZM20,15H19a1,1,0,0,1,0-2h1Zm0-4H19a3,3,0,0,0,0,6h1v1a1,1,0,0,1-1,1H5a1,1,0,0,1-1-1V8.83A3,3,0,0,0,5,9H19a1,1,0,0,1,1,1Z"/>
            </svg>
            <span>Connect</span>
          </button>
          <!-- end wallet -->
        </div>
      </div>
    </div>
  </div>
</header>

<slot/>

<!-- wallet modal -->
<div class="modal modal--auto fade" id="modal-wallet" tabindex="-1" aria-labelledby="modal-wallet" aria-hidden="true">
  <div class="modal-dialog modal-dialog-centered">
    <div class="modal-content">
      <div class="modal__content">
        <button class="modal__close" type="button" data-bs-dismiss="modal" aria-label="Close">
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24">
            <path d="M13.41,12l6.3-6.29a1,1,0,1,0-1.42-1.42L12,10.59,5.71,4.29A1,1,0,0,0,4.29,5.71L10.59,12l-6.3,6.29a1,1,0,0,0,0,1.42,1,1,0,0,0,1.42,0L12,13.41l6.29,6.3a1,1,0,0,0,1.42,0,1,1,0,0,0,0-1.42Z"/>
          </svg>
        </button>

        <h4 class="modal__title">Connect Wallet</h4>

        <p class="modal__text">Choose one of available wallet providers or create a new wallet.</p>

        <!-- Wallet options -->
	<a href="/" class="modal__wallet">
						<img src="img/wallet/metamask.svg" alt="">
						<span>MetaMask</span>
					</a>

					<a href="/" class="modal__wallet">
						<img src="img/wallet/coinbase.svg" alt="">
						<span>Coinbase Wallet</span>
					</a>

					<a href="/" class="modal__wallet">
						<img src="img/wallet/walletconnect.svg" alt="">
						<span>WalletConnect</span>
					</a>

					<a href="/" class="modal__wallet">
						<img src="img/wallet/myetherwallet.svg" alt="">
						<span>MyEtherWallet</span>
					</a>

					<a href="/" class="modal__wallet">
						<img src="img/wallet/fortmatic.svg" alt="">
						<span>Fortmatic</span>
					</a>
      </div>
    </div>
  </div>
</div>
<!-- end wallet modal -->
