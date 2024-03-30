<script>
  import { onMount } from 'svelte/internal';
  import { getAuth } from 'firebase/auth';
  import { app } from '../../firebase';
  import { goto } from '$app/navigation';

  const auth = getAuth(app);
  let user;

  onMount(() => {
    const unsubscribe = auth.onAuthStateChanged((currentUser) => {
      user = currentUser;
      if (!user) {
        goto('/login');
      }
    });

    return unsubscribe;
  });

  function logout() {
    auth.signOut();
  }
</script>

	<!-- page wrap -->
	{#if user}
	<div class="section section--content">
		<div class="section__content">
			<!-- error -->
			<!-- hero content -->
					<div class="hero__content">
					
						<div class="header__logo">
						     {#if user.photoURL}
        <img src="{user.photoURL}" alt="profile-pic" class="header__logo">
      {/if}
						</div>
						<h2 class="hero__title">Welcome {user.displayName}</h2>
						<p class="hero__text">{user.email}</p>
						<div class="hero__btns">
							<button class="hero__btn"><span>Explore</span></button>
							<button on:click={logout} class="hero__btn hero__btn--nephrite"><span>Logout</span></button>
						</div>
						


						<!-- bg animation -->
						<div id="canvas" class="hero__canvas"></div>
						<!-- end bg animation -->
					</div>
					<!-- end hero content -->
		</div>

		<!-- bg animation -->
		<div id="canvas2" class="section__canvas"></div>
		<!-- end bg animation -->
	</div>
	<!-- end page wrap -->
 {:else}
  <p>Loading...</p>
{/if}
