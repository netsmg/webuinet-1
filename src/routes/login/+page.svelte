<script>
   import { getAuth, signInWithEmailAndPassword, GoogleAuthProvider, FacebookAuthProvider, TwitterAuthProvider, signInWithPopup } from 'firebase/auth';
  import { goto } from '$app/navigation';
  import { app } from '../../firebase';
  
  const auth = getAuth(app);
  let email = '';
  let password = '';
  let errorMessage = '';

  async function login() {
    // Clear previous error message
    errorMessage = '';

    // Validate email
    if (!email.trim()) {
        errorMessage = 'Email is required.';
    } else if (!/\S+@\S+\.\S+/.test(email)) {
        errorMessage = 'Email is invalid.';
    }

    // Validate password
    if (!password.trim()) {
        errorMessage = 'Password is required.';
    } else if (password.length < 6) {
        errorMessage = 'Password must be at least 6 characters long.';
    }

    // If there are validation errors, display error message and return
    if (errorMessage) {
        console.error('Login error:', errorMessage);
        return;
    }

    try {
        const userCredential = await signInWithEmailAndPassword(auth, email, password);
        // User is signed in
        const user = userCredential.user;
        console.log('Logged in user:', user);
        goto('/');
    } catch (error) {
        errorMessage = error.message;
        console.error('Login error:', errorMessage);
    }
  }

  async function loginWithGoogle() {
    const provider = new GoogleAuthProvider();
    try {
        const userCredential = await signInWithPopup(auth, provider);
        // User is signed in
        const user = userCredential.user;
        console.log('Logged in user:', user);
        goto('/');
    } catch (error) {
        errorMessage = error.message;
        console.error('Login with Google error:', errorMessage);
    }
  }

  async function loginWithFacebook() {
    const provider = new FacebookAuthProvider();
    try {
        const userCredential = await signInWithPopup(auth, provider);
        // User is signed in
        const user = userCredential.user;
        console.log('Logged in user:', user);
        goto('/');
    } catch (error) {
        errorMessage = error.message;
        console.error('Login with Facebook error:', errorMessage);
    }
  }

  async function loginWithTwitter() {
    const provider = new TwitterAuthProvider();
    try {
        const userCredential = await signInWithPopup(auth, provider);
        // User is signed in
        const user = userCredential.user;
        console.log('Logged in user:', user);
        goto('/');
    } catch (error) {
        errorMessage = error.message;
        console.error('Login with Twitter error:', errorMessage);
    }
  }
</script>

<link rel="stylesheet" href="css/bootstrap.min.css">
	<link rel="stylesheet" href="css/blueimp-gallery.min.css">
	<link rel="stylesheet" href="css/splide.min.css">
	<link rel="stylesheet" href="css/slimselect.css">
	<link rel="stylesheet" href="css/main.css">

<!-- page wrap -->
	<div class="section section--content">
		<div class="section__content">
			<!-- form -->
			<form  class="form form--content" on:submit|preventDefault={login}>
				<div class="form__logo-wrap">
					
						<svg width="50" height="50" viewBox="0 0 50 50" fill="none" xmlns="http://www.w3.org/2000/svg">
<rect width="50" height="50" rx="18" fill="#AA72CE" fill-opacity="0.12"/>
<g filter="url(#filter0_d_76_4)">
<path d="M13.9417 35.667L23.5919 14H26.3272L36.1312 35.667H32.8427L30.1689 29.5204L31.5212 30.3809H18.398L19.8425 29.5204L17.1687 35.667H13.9417ZM24.9135 17.5036L20.242 28.5369L19.5044 27.83H30.4148L29.8001 28.5369L25.0364 17.5036H24.9135Z" fill="#AA72CE"/>
</g>
<g filter="url(#filter1_d_76_4)">
<path d="M12.1769 27.7642H37.7995L39 30.3985H11L12.1769 27.7642Z" fill="#AA72CE"/>
</g>
<defs>
<filter id="filter0_d_76_4" x="9.94165" y="10" width="30.1895" height="29.6671" filterUnits="userSpaceOnUse" color-interpolation-filters="sRGB">
<feFlood flood-opacity="0" result="BackgroundImageFix"/>
<feColorMatrix in="SourceAlpha" type="matrix" values="0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 127 0" result="hardAlpha"/>
<feOffset/>
<feGaussianBlur stdDeviation="2"/>
<feComposite in2="hardAlpha" operator="out"/>
<feColorMatrix type="matrix" values="0 0 0 0 0.666667 0 0 0 0 0.447059 0 0 0 0 0.807843 0 0 0 0.4 0"/>
<feBlend mode="normal" in2="BackgroundImageFix" result="effect1_dropShadow_76_4"/>
<feBlend mode="normal" in="SourceGraphic" in2="effect1_dropShadow_76_4" result="shape"/>
</filter>
<filter id="filter1_d_76_4" x="9" y="25.7642" width="32" height="6.63428" filterUnits="userSpaceOnUse" color-interpolation-filters="sRGB">
<feFlood flood-opacity="0" result="BackgroundImageFix"/>
<feColorMatrix in="SourceAlpha" type="matrix" values="0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 127 0" result="hardAlpha"/>
<feOffset/>
<feGaussianBlur stdDeviation="1"/>
<feComposite in2="hardAlpha" operator="out"/>
<feColorMatrix type="matrix" values="0 0 0 0 0.666667 0 0 0 0 0.447059 0 0 0 0 0.807843 0 0 0 0.4 0"/>
<feBlend mode="normal" in2="BackgroundImageFix" result="effect1_dropShadow_76_4"/>
<feBlend mode="normal" in="SourceGraphic" in2="effect1_dropShadow_76_4" result="shape"/>
</filter>
</defs>
</svg>

					
					<span class="form__tagline">Welcome to WEBUInet</span>
					
				</div>
<div>
    {#if errorMessage}
  <p style="color: red;">{errorMessage}</p>
{/if}
</div>

				<div class="form__group">
					<input type="email" id="email" bind:value={email} class="form__input" placeholder="Email">
				</div>

				<div class="form__group">
					<input type="password" id="password" bind:value={password} class="form__input" placeholder="Password">
				</div>

				<div class="form__group form__group--checkbox">
					<input id="remember"  name="remember" type="checkbox">
					<label for="remember">Remember Me</label>
				</div>
				
				<button class="form__btn" type="submit">Sign in</button>

				<span class="form__delimiter">or</span>

				<div class="form__social">
					<a class="fb" on:click={loginWithFacebook} ><svg viewBox="0 0 9 17" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M5.56341 16.8197V8.65888H7.81615L8.11468 5.84663H5.56341L5.56724 4.43907C5.56724 3.70559 5.63693 3.31257 6.69042 3.31257H8.09873V0.5H5.84568C3.1394 0.5 2.18686 1.86425 2.18686 4.15848V5.84695H0.499939V8.6592H2.18686V16.8197H5.56341Z"/></svg></a>
					<a class="tw" on:click={loginWithTwitter}><svg viewBox="0 0 16 12" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M7.55075 3.19219L7.58223 3.71122L7.05762 3.64767C5.14804 3.40404 3.47978 2.57782 2.06334 1.1902L1.37085 0.501686L1.19248 1.01013C0.814766 2.14353 1.05609 3.34048 1.843 4.14552C2.26269 4.5904 2.16826 4.65396 1.4443 4.38914C1.19248 4.3044 0.972149 4.24085 0.951164 4.27263C0.877719 4.34677 1.12953 5.31069 1.32888 5.69202C1.60168 6.22165 2.15777 6.74068 2.76631 7.04787L3.28043 7.2915L2.67188 7.30209C2.08432 7.30209 2.06334 7.31268 2.12629 7.53512C2.33613 8.22364 3.16502 8.95452 4.08833 9.2723L4.73884 9.49474L4.17227 9.8337C3.33289 10.321 2.34663 10.5964 1.36036 10.6175C0.888211 10.6281 0.5 10.6705 0.5 10.7023C0.5 10.8082 1.78005 11.4014 2.52499 11.6344C4.75983 12.3229 7.41435 12.0264 9.40787 10.8506C10.8243 10.0138 12.2408 8.35075 12.9018 6.74068C13.2585 5.88269 13.6152 4.315 13.6152 3.56293C13.6152 3.07567 13.6467 3.01212 14.2343 2.42953C14.5805 2.09056 14.9058 1.71983 14.9687 1.6139C15.0737 1.41264 15.0632 1.41264 14.5281 1.59272C13.6362 1.91049 13.5103 1.86812 13.951 1.39146C14.2762 1.0525 14.6645 0.438131 14.6645 0.258058C14.6645 0.22628 14.5071 0.279243 14.3287 0.374576C14.1398 0.480501 13.7202 0.639389 13.4054 0.734722L12.8388 0.914795L12.3247 0.565241C12.0414 0.374576 11.6427 0.162725 11.4329 0.0991699C10.8978 -0.0491255 10.0794 -0.0279404 9.59673 0.14154C8.2852 0.618204 7.45632 1.84694 7.55075 3.19219Z"/></svg></a>
					<a on:click={loginWithGoogle} class="gl"><svg xmlns='http://www.w3.org/2000/svg' class='ionicon' viewBox='0 0 512 512'><path d='M473.16 221.48l-2.26-9.59H262.46v88.22H387c-12.93 61.4-72.93 93.72-121.94 93.72-35.66 0-73.25-15-98.13-39.11a140.08 140.08 0 01-41.8-98.88c0-37.16 16.7-74.33 41-98.78s61-38.13 97.49-38.13c41.79 0 71.74 22.19 82.94 32.31l62.69-62.36C390.86 72.72 340.34 32 261.6 32c-60.75 0-119 23.27-161.58 65.71C58 139.5 36.25 199.93 36.25 256s20.58 113.48 61.3 155.6c43.51 44.92 105.13 68.4 168.58 68.4 57.73 0 112.45-22.62 151.45-63.66 38.34-40.4 58.17-96.3 58.17-154.9 0-24.67-2.48-39.32-2.59-39.96z'/></svg></a>
				</div>

				<span class="form__text form__text--center">Don&apos;t have an account? <a href="/register">Register!</a><br> <a href="/forgot">Forgot password?</a></span>
			</form>
			<!-- end form -->
		</div>

		<!-- bg animation -->
		<div id="canvas2" class="section__canvas"></div>
		<!-- end bg animation -->
	</div>
	<!-- end page wrap -->
	

