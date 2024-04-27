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
        // Use SweetAlert to show error message
        await Swal.fire({
            icon: 'error',
            title: 'Login Error',
            text: errorMessage
        });
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
        // Use SweetAlert to show error message
        await Swal.fire({
            icon: 'error',
            title: 'Login Error',
            text: errorMessage
        });
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
await Swal.fire({
            icon: 'error',
            title: 'Login Error',
            text: errorMessage
        });
        return;
         
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
        await Swal.fire({
            icon: 'error',
            title: 'Login Error',
            text: errorMessage
        });
        return;
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
        await Swal.fire({
            icon: 'error',
            title: 'Login Error',
            text: errorMessage
        });
        return;
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
					<svg xmlns="http://www.w3.org/2000/svg" version="1.1" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:svgjs="http://svgjs.dev/svgjs" width="55" height="55" viewBox="0 0 1500 1500"><rect width="55" height="55" fill="#000000"></rect><g transform="matrix(0.6666666666666666,0,0,0.6666666666666666,249.39393939393938,438.5856950067477)"><svg viewBox="0 0 396 247" data-background-color="#000000" preserveAspectRatio="xMidYMid meet" height="935" width="1500" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink"><g id="tight-bounds" transform="matrix(1,0,0,1,0.2400000000000091,-0.09999999999999432)"><svg viewBox="0 0 395.52 247.2" height="247.2" width="395.52"><rect width="395.52" height="247.2" fill="url(#90ff3bf0-ffd8-47e9-9131-8ec53239fb3c)" mask="url(#beb316f0-9929-46ce-a602-d53eba9a2ca1)" data-fill-palette-color="tertiary"></rect><g><svg></svg></g><g><svg viewBox="0 0 395.52 247.2" height="247.2" width="395.52"><mask id="684aeb9f-56dd-430a-978a-41b3403ece50"><rect width="395.52" height="247.2" fill="white"></rect><g transform="matrix(1,0,0,1,0,89.09954770622443)" id="clone"><svg viewBox="0 0 395.52 69.00090458755115" height="69.00090458755115" width="395.52"><g><svg viewBox="0 0 395.52 69.00090458755115" height="69.00090458755115" width="395.52"><g><svg viewBox="0 0 395.52 69.00090458755115" height="69.00090458755115" width="395.52"><g><svg viewBox="0 0 395.52 69.00090458755115" height="69.00090458755115" width="395.52"><g id="SvgjsG1272"><svg viewBox="0 0 395.52 69.00090458755115" height="69.00090458755115" width="395.52" id="SvgjsSvg1271"><g><svg viewBox="0 0 395.52 69.00090458755115" height="69.00090458755115" width="395.52"><g transform="matrix(1,0,0,1,0,0)"><svg width="395.52" viewBox="-2.15 -38 233.13 41.5" height="69.00090458755115" data-palette-color="url(#6f9de062-2887-414b-be43-2e83111382c1)"><path d="M37.15-33.5L5.85-33.5 5.85-35 39.3-35 26.55 0.05 20.05-17.75 13.6 0.05 0.85-35 2.45-35 13.6-4.35 20.05-22.15 26.55-4.35 37.15-33.5ZM63.05-19.8L63.05-18.3 48.2-18.3 63.5-33.5 46.6-33.5 46.6-1.5 66-1.5 66 0 45.1 0 45.1-35 67.15-35 51.85-19.8 63.05-19.8ZM81.9 0L81.9 0 73.9 0 73.9-35 80-35Q86.6-35 89.95-32.58 93.3-30.15 93.3-25.75L93.3-25.75Q93.3-20.75 89.1-18.4L89.1-18.4Q95.2-16.1 95.2-9.75L95.2-9.75Q95.2-5.25 91.9-2.63 88.6 0 81.9 0ZM75.4-1.5L81.9-1.5Q84.25-1.5 86.2-1.88 88.15-2.25 89.92-3.13 91.7-4 92.7-5.7 93.7-7.4 93.7-9.75L93.7-9.75Q93.7-15.1 88.55-17L88.55-17 85.55-18.1 88.35-19.7Q91.8-21.6 91.8-25.75L91.8-25.75Q91.8-33.5 80-33.5L80-33.5 75.4-33.5 75.4-1.5ZM106.54-33.5L106.54-35 125.69-35 125.69-15.05Q125.69-7.05 122.94-3.28 120.19 0.5 114.04 0.5 107.89 0.5 105.14-3.28 102.39-7.05 102.39-15.05L102.39-15.05 102.39-35 103.89-35 103.89-15.05Q103.89-10.9 104.59-8.08 105.29-5.25 106.69-3.75 108.09-2.25 109.84-1.63 111.59-1 114.04-1 116.49-1 118.24-1.63 119.99-2.25 121.39-3.75 122.79-5.25 123.49-8.08 124.19-10.9 124.19-15.05L124.19-15.05 124.19-33.5 106.54-33.5ZM136.64-35L136.64 0 135.14 0 135.14-35 136.64-35ZM150.44 0L150.44-1.5 165.94-1.5 148.04-32.45 148.04 0 146.54 0 146.54-35 148.29-35 166.99-2.65 166.99-35 168.49-35 168.49 0 150.44 0ZM196.34-19.8L196.34-18.3 181.49-18.3 196.79-33.5 179.89-33.5 179.89-1.5 199.29-1.5 199.29 0 178.39 0 178.39-35 200.44-35 185.14-19.8 196.34-19.8ZM202.98-35L227.98-35 227.98-33.5 216.23-33.5 216.23 0 214.73 0 214.73-33.5 202.98-33.5 202.98-35Z" opacity="1" transform="matrix(1,0,0,1,0,0)" fill="black" class="wordmark-text-0" id="SvgjsPath1270" stroke-width="5" stroke="black" stroke-linejoin="round"></path></svg></g></svg></g></svg></g></svg></g></svg></g></svg></g></svg></g></mask><g mask="url(#684aeb9f-56dd-430a-978a-41b3403ece50)"><g><path d="M318.186 10.579h-220.752v-10.579h235.916l-89.923 247.2-45.843-125.54-45.491 125.54-89.923-247.2h11.285l78.638 216.168 45.491-125.54 45.843 125.54z" fill="url(#90ff3bf0-ffd8-47e9-9131-8ec53239fb3c)" fill-rule="nonzero" stroke="none" stroke-width="1" stroke-linecap="butt" stroke-linejoin="miter" stroke-miterlimit="10" stroke-dasharray="" stroke-dashoffset="0" font-family="none" font-weight="none" font-size="none" text-anchor="none" style="mix-blend-mode: normal" data-fill-palette-color="tertiary"></path></g></g><g transform="matrix(1,0,0,1,0,89.09954770622443)"><svg viewBox="0 0 395.52 69.00090458755115" height="69.00090458755115" width="395.52"><g><svg viewBox="0 0 395.52 69.00090458755115" height="69.00090458755115" width="395.52"><g><svg viewBox="0 0 395.52 69.00090458755115" height="69.00090458755115" width="395.52"><g><svg viewBox="0 0 395.52 69.00090458755115" height="69.00090458755115" width="395.52"><g id="textblocktransform"><svg viewBox="0 0 395.52 69.00090458755115" height="69.00090458755115" width="395.52" id="textblock"><g><svg viewBox="0 0 395.52 69.00090458755115" height="69.00090458755115" width="395.52"><g transform="matrix(1,0,0,1,0,0)"><svg width="395.52" viewBox="-2.15 -38 233.13 41.5" height="69.00090458755115" data-palette-color="url(#6f9de062-2887-414b-be43-2e83111382c1)"></svg></g></svg></g></svg></g></svg></g></svg></g></svg></g></svg></g></svg></g><defs></defs><mask id="c609411e-7183-4421-a21a-a2222ef2dce5"><g id="SvgjsG1282"><svg viewBox="0 0 395.52 247.2" height="247.2" width="395.52"><g><svg></svg></g><g><svg viewBox="0 0 395.52 247.2" height="247.2" width="395.52"><mask id="SvgjsMask1281"><rect width="395.52" height="247.2" fill="black"></rect><g transform="matrix(1,0,0,1,0,89.09954770622443)" id="SvgjsG1280"><svg viewBox="0 0 395.52 69.00090458755115" height="69.00090458755115" width="395.52"><g><svg viewBox="0 0 395.52 69.00090458755115" height="69.00090458755115" width="395.52"><g><svg viewBox="0 0 395.52 69.00090458755115" height="69.00090458755115" width="395.52"><g><svg viewBox="0 0 395.52 69.00090458755115" height="69.00090458755115" width="395.52"><g id="SvgjsG1279"><svg viewBox="0 0 395.52 69.00090458755115" height="69.00090458755115" width="395.52" id="SvgjsSvg1278"><g><svg viewBox="0 0 395.52 69.00090458755115" height="69.00090458755115" width="395.52"><g transform="matrix(1,0,0,1,0,0)"><svg width="395.52" viewBox="-2.15 -38 233.13 41.5" height="69.00090458755115" data-palette-color="url(#6f9de062-2887-414b-be43-2e83111382c1)"><path d="M37.15-33.5L5.85-33.5 5.85-35 39.3-35 26.55 0.05 20.05-17.75 13.6 0.05 0.85-35 2.45-35 13.6-4.35 20.05-22.15 26.55-4.35 37.15-33.5ZM63.05-19.8L63.05-18.3 48.2-18.3 63.5-33.5 46.6-33.5 46.6-1.5 66-1.5 66 0 45.1 0 45.1-35 67.15-35 51.85-19.8 63.05-19.8ZM81.9 0L81.9 0 73.9 0 73.9-35 80-35Q86.6-35 89.95-32.58 93.3-30.15 93.3-25.75L93.3-25.75Q93.3-20.75 89.1-18.4L89.1-18.4Q95.2-16.1 95.2-9.75L95.2-9.75Q95.2-5.25 91.9-2.63 88.6 0 81.9 0ZM75.4-1.5L81.9-1.5Q84.25-1.5 86.2-1.88 88.15-2.25 89.92-3.13 91.7-4 92.7-5.7 93.7-7.4 93.7-9.75L93.7-9.75Q93.7-15.1 88.55-17L88.55-17 85.55-18.1 88.35-19.7Q91.8-21.6 91.8-25.75L91.8-25.75Q91.8-33.5 80-33.5L80-33.5 75.4-33.5 75.4-1.5ZM106.54-33.5L106.54-35 125.69-35 125.69-15.05Q125.69-7.05 122.94-3.28 120.19 0.5 114.04 0.5 107.89 0.5 105.14-3.28 102.39-7.05 102.39-15.05L102.39-15.05 102.39-35 103.89-35 103.89-15.05Q103.89-10.9 104.59-8.08 105.29-5.25 106.69-3.75 108.09-2.25 109.84-1.63 111.59-1 114.04-1 116.49-1 118.24-1.63 119.99-2.25 121.39-3.75 122.79-5.25 123.49-8.08 124.19-10.9 124.19-15.05L124.19-15.05 124.19-33.5 106.54-33.5ZM136.64-35L136.64 0 135.14 0 135.14-35 136.64-35ZM150.44 0L150.44-1.5 165.94-1.5 148.04-32.45 148.04 0 146.54 0 146.54-35 148.29-35 166.99-2.65 166.99-35 168.49-35 168.49 0 150.44 0ZM196.34-19.8L196.34-18.3 181.49-18.3 196.79-33.5 179.89-33.5 179.89-1.5 199.29-1.5 199.29 0 178.39 0 178.39-35 200.44-35 185.14-19.8 196.34-19.8ZM202.98-35L227.98-35 227.98-33.5 216.23-33.5 216.23 0 214.73 0 214.73-33.5 202.98-33.5 202.98-35Z" opacity="1" transform="matrix(1,0,0,1,0,0)" fill="black" class="wordmark-text-0" id="SvgjsPath1277" stroke-width="5" stroke="black" stroke-linejoin="round"></path></svg></g></svg></g></svg></g></svg></g></svg></g></svg></g></svg></g></mask><g mask="url(#684aeb9f-56dd-430a-978a-41b3403ece50)"><g><path d="M318.186 10.579h-220.752v-10.579h235.916l-89.923 247.2-45.843-125.54-45.491 125.54-89.923-247.2h11.285l78.638 216.168 45.491-125.54 45.843 125.54z" fill="black" fill-rule="nonzero" stroke="none" stroke-width="1" stroke-linecap="butt" stroke-linejoin="miter" stroke-miterlimit="10" stroke-dasharray="" stroke-dashoffset="0" font-family="none" font-weight="none" font-size="none" text-anchor="none" style="mix-blend-mode: normal"></path></g></g><g transform="matrix(1,0,0,1,0,89.09954770622443)"><svg viewBox="0 0 395.52 69.00090458755115" height="69.00090458755115" width="395.52"><g><svg viewBox="0 0 395.52 69.00090458755115" height="69.00090458755115" width="395.52"><g><svg viewBox="0 0 395.52 69.00090458755115" height="69.00090458755115" width="395.52"><g><svg viewBox="0 0 395.52 69.00090458755115" height="69.00090458755115" width="395.52"><g id="SvgjsG1276"><svg viewBox="0 0 395.52 69.00090458755115" height="69.00090458755115" width="395.52" id="SvgjsSvg1275"><g><svg viewBox="0 0 395.52 69.00090458755115" height="69.00090458755115" width="395.52"><g transform="matrix(1,0,0,1,0,0)"><svg width="395.52" viewBox="-2.15 -38 233.13 41.5" height="69.00090458755115" data-palette-color="url(#6f9de062-2887-414b-be43-2e83111382c1)"><path d="M37.15-33.5L5.85-33.5 5.85-35 39.3-35 26.55 0.05 20.05-17.75 13.6 0.05 0.85-35 2.45-35 13.6-4.35 20.05-22.15 26.55-4.35 37.15-33.5ZM63.05-19.8L63.05-18.3 48.2-18.3 63.5-33.5 46.6-33.5 46.6-1.5 66-1.5 66 0 45.1 0 45.1-35 67.15-35 51.85-19.8 63.05-19.8ZM81.9 0L81.9 0 73.9 0 73.9-35 80-35Q86.6-35 89.95-32.58 93.3-30.15 93.3-25.75L93.3-25.75Q93.3-20.75 89.1-18.4L89.1-18.4Q95.2-16.1 95.2-9.75L95.2-9.75Q95.2-5.25 91.9-2.63 88.6 0 81.9 0ZM75.4-1.5L81.9-1.5Q84.25-1.5 86.2-1.88 88.15-2.25 89.92-3.13 91.7-4 92.7-5.7 93.7-7.4 93.7-9.75L93.7-9.75Q93.7-15.1 88.55-17L88.55-17 85.55-18.1 88.35-19.7Q91.8-21.6 91.8-25.75L91.8-25.75Q91.8-33.5 80-33.5L80-33.5 75.4-33.5 75.4-1.5ZM106.54-33.5L106.54-35 125.69-35 125.69-15.05Q125.69-7.05 122.94-3.28 120.19 0.5 114.04 0.5 107.89 0.5 105.14-3.28 102.39-7.05 102.39-15.05L102.39-15.05 102.39-35 103.89-35 103.89-15.05Q103.89-10.9 104.59-8.08 105.29-5.25 106.69-3.75 108.09-2.25 109.84-1.63 111.59-1 114.04-1 116.49-1 118.24-1.63 119.99-2.25 121.39-3.75 122.79-5.25 123.49-8.08 124.19-10.9 124.19-15.05L124.19-15.05 124.19-33.5 106.54-33.5ZM136.64-35L136.64 0 135.14 0 135.14-35 136.64-35ZM150.44 0L150.44-1.5 165.94-1.5 148.04-32.45 148.04 0 146.54 0 146.54-35 148.29-35 166.99-2.65 166.99-35 168.49-35 168.49 0 150.44 0ZM196.34-19.8L196.34-18.3 181.49-18.3 196.79-33.5 179.89-33.5 179.89-1.5 199.29-1.5 199.29 0 178.39 0 178.39-35 200.44-35 185.14-19.8 196.34-19.8ZM202.98-35L227.98-35 227.98-33.5 216.23-33.5 216.23 0 214.73 0 214.73-33.5 202.98-33.5 202.98-35Z" opacity="1" transform="matrix(1,0,0,1,0,0)" fill="white" class="wordmark-text-0" id="SvgjsPath1274"></path></svg></g></svg></g></svg></g></svg></g></svg></g></svg></g></svg></g></svg></g><defs><mask></mask></defs></svg><rect width="395.52" height="247.2" fill="black" stroke="none" visibility="hidden"></rect></g></mask><linearGradient x1="0.054" x2="0.941" y1="0.5" y2="0.5" id="6f9de062-2887-414b-be43-2e83111382c1"><stop stop-color="#864d25" offset="0"></stop><stop stop-color="#f1c4b3" offset="0.498"></stop><stop stop-color="#864d25" offset="1"></stop></linearGradient><rect width="395.52" height="247.2" fill="url(#6f9de062-2887-414b-be43-2e83111382c1)" mask="url(#c609411e-7183-4421-a21a-a2222ef2dce5)" data-fill-palette-color="primary"></rect><mask id="beb316f0-9929-46ce-a602-d53eba9a2ca1"><g id="SvgjsG1335"><svg viewBox="0 0 395.52 247.2" height="247.2" width="395.52"><g><svg></svg></g><g><svg viewBox="0 0 395.52 247.2" height="247.2" width="395.52"><mask id="SvgjsMask1334"><rect width="395.52" height="247.2" fill="black"></rect><g transform="matrix(1,0,0,1,0,89.09954770622443)" id="SvgjsG1333"><svg viewBox="0 0 395.52 69.00090458755115" height="69.00090458755115" width="395.52"><g><svg viewBox="0 0 395.52 69.00090458755115" height="69.00090458755115" width="395.52"><g><svg viewBox="0 0 395.52 69.00090458755115" height="69.00090458755115" width="395.52"><g><svg viewBox="0 0 395.52 69.00090458755115" height="69.00090458755115" width="395.52"><g id="SvgjsG1332"><svg viewBox="0 0 395.52 69.00090458755115" height="69.00090458755115" width="395.52" id="SvgjsSvg1331"><g><svg viewBox="0 0 395.52 69.00090458755115" height="69.00090458755115" width="395.52"><g transform="matrix(1,0,0,1,0,0)"><svg width="395.52" viewBox="-2.15 -38 233.13 41.5" height="69.00090458755115" data-palette-color="url(#6f9de062-2887-414b-be43-2e83111382c1)"><path d="M37.15-33.5L5.85-33.5 5.85-35 39.3-35 26.55 0.05 20.05-17.75 13.6 0.05 0.85-35 2.45-35 13.6-4.35 20.05-22.15 26.55-4.35 37.15-33.5ZM63.05-19.8L63.05-18.3 48.2-18.3 63.5-33.5 46.6-33.5 46.6-1.5 66-1.5 66 0 45.1 0 45.1-35 67.15-35 51.85-19.8 63.05-19.8ZM81.9 0L81.9 0 73.9 0 73.9-35 80-35Q86.6-35 89.95-32.58 93.3-30.15 93.3-25.75L93.3-25.75Q93.3-20.75 89.1-18.4L89.1-18.4Q95.2-16.1 95.2-9.75L95.2-9.75Q95.2-5.25 91.9-2.63 88.6 0 81.9 0ZM75.4-1.5L81.9-1.5Q84.25-1.5 86.2-1.88 88.15-2.25 89.92-3.13 91.7-4 92.7-5.7 93.7-7.4 93.7-9.75L93.7-9.75Q93.7-15.1 88.55-17L88.55-17 85.55-18.1 88.35-19.7Q91.8-21.6 91.8-25.75L91.8-25.75Q91.8-33.5 80-33.5L80-33.5 75.4-33.5 75.4-1.5ZM106.54-33.5L106.54-35 125.69-35 125.69-15.05Q125.69-7.05 122.94-3.28 120.19 0.5 114.04 0.5 107.89 0.5 105.14-3.28 102.39-7.05 102.39-15.05L102.39-15.05 102.39-35 103.89-35 103.89-15.05Q103.89-10.9 104.59-8.08 105.29-5.25 106.69-3.75 108.09-2.25 109.84-1.63 111.59-1 114.04-1 116.49-1 118.24-1.63 119.99-2.25 121.39-3.75 122.79-5.25 123.49-8.08 124.19-10.9 124.19-15.05L124.19-15.05 124.19-33.5 106.54-33.5ZM136.64-35L136.64 0 135.14 0 135.14-35 136.64-35ZM150.44 0L150.44-1.5 165.94-1.5 148.04-32.45 148.04 0 146.54 0 146.54-35 148.29-35 166.99-2.65 166.99-35 168.49-35 168.49 0 150.44 0ZM196.34-19.8L196.34-18.3 181.49-18.3 196.79-33.5 179.89-33.5 179.89-1.5 199.29-1.5 199.29 0 178.39 0 178.39-35 200.44-35 185.14-19.8 196.34-19.8ZM202.98-35L227.98-35 227.98-33.5 216.23-33.5 216.23 0 214.73 0 214.73-33.5 202.98-33.5 202.98-35Z" opacity="1" transform="matrix(1,0,0,1,0,0)" fill="black" class="wordmark-text-0" id="SvgjsPath1330" stroke-width="5" stroke="black" stroke-linejoin="round"></path></svg></g></svg></g></svg></g></svg></g></svg></g></svg></g></svg></g></mask><g mask="url(#684aeb9f-56dd-430a-978a-41b3403ece50)"><g><path d="M318.186 10.579h-220.752v-10.579h235.916l-89.923 247.2-45.843-125.54-45.491 125.54-89.923-247.2h11.285l78.638 216.168 45.491-125.54 45.843 125.54z" fill="white" fill-rule="nonzero" stroke="none" stroke-width="1" stroke-linecap="butt" stroke-linejoin="miter" stroke-miterlimit="10" stroke-dasharray="" stroke-dashoffset="0" font-family="none" font-weight="none" font-size="none" text-anchor="none" style="mix-blend-mode: normal"></path></g></g><g transform="matrix(1,0,0,1,0,89.09954770622443)"><svg viewBox="0 0 395.52 69.00090458755115" height="69.00090458755115" width="395.52"><g><svg viewBox="0 0 395.52 69.00090458755115" height="69.00090458755115" width="395.52"><g><svg viewBox="0 0 395.52 69.00090458755115" height="69.00090458755115" width="395.52"><g><svg viewBox="0 0 395.52 69.00090458755115" height="69.00090458755115" width="395.52"><g id="SvgjsG1329"><svg viewBox="0 0 395.52 69.00090458755115" height="69.00090458755115" width="395.52" id="SvgjsSvg1328"><g><svg viewBox="0 0 395.52 69.00090458755115" height="69.00090458755115" width="395.52"><g transform="matrix(1,0,0,1,0,0)"><svg width="395.52" viewBox="-2.15 -38 233.13 41.5" height="69.00090458755115" data-palette-color="url(#6f9de062-2887-414b-be43-2e83111382c1)"></svg></g></svg></g></svg></g></svg></g></svg></g></svg></g></svg></g></svg></g><defs><mask></mask></defs><mask><g id="SvgjsG1327"><svg viewBox="0 0 395.52 247.2" height="247.2" width="395.52"><g><svg></svg></g><g><svg viewBox="0 0 395.52 247.2" height="247.2" width="395.52"><mask id="SvgjsMask1326"><rect width="395.52" height="247.2" fill="black"></rect><g transform="matrix(1,0,0,1,0,89.09954770622443)" id="SvgjsG1325"><svg viewBox="0 0 395.52 69.00090458755115" height="69.00090458755115" width="395.52"><g><svg viewBox="0 0 395.52 69.00090458755115" height="69.00090458755115" width="395.52"><g><svg viewBox="0 0 395.52 69.00090458755115" height="69.00090458755115" width="395.52"><g><svg viewBox="0 0 395.52 69.00090458755115" height="69.00090458755115" width="395.52"><g id="SvgjsG1324"><svg viewBox="0 0 395.52 69.00090458755115" height="69.00090458755115" width="395.52" id="SvgjsSvg1323"><g><svg viewBox="0 0 395.52 69.00090458755115" height="69.00090458755115" width="395.52"><g transform="matrix(1,0,0,1,0,0)"><svg width="395.52" viewBox="-2.15 -38 233.13 41.5" height="69.00090458755115" data-palette-color="url(#6f9de062-2887-414b-be43-2e83111382c1)"><path d="M37.15-33.5L5.85-33.5 5.85-35 39.3-35 26.55 0.05 20.05-17.75 13.6 0.05 0.85-35 2.45-35 13.6-4.35 20.05-22.15 26.55-4.35 37.15-33.5ZM63.05-19.8L63.05-18.3 48.2-18.3 63.5-33.5 46.6-33.5 46.6-1.5 66-1.5 66 0 45.1 0 45.1-35 67.15-35 51.85-19.8 63.05-19.8ZM81.9 0L81.9 0 73.9 0 73.9-35 80-35Q86.6-35 89.95-32.58 93.3-30.15 93.3-25.75L93.3-25.75Q93.3-20.75 89.1-18.4L89.1-18.4Q95.2-16.1 95.2-9.75L95.2-9.75Q95.2-5.25 91.9-2.63 88.6 0 81.9 0ZM75.4-1.5L81.9-1.5Q84.25-1.5 86.2-1.88 88.15-2.25 89.92-3.13 91.7-4 92.7-5.7 93.7-7.4 93.7-9.75L93.7-9.75Q93.7-15.1 88.55-17L88.55-17 85.55-18.1 88.35-19.7Q91.8-21.6 91.8-25.75L91.8-25.75Q91.8-33.5 80-33.5L80-33.5 75.4-33.5 75.4-1.5ZM106.54-33.5L106.54-35 125.69-35 125.69-15.05Q125.69-7.05 122.94-3.28 120.19 0.5 114.04 0.5 107.89 0.5 105.14-3.28 102.39-7.05 102.39-15.05L102.39-15.05 102.39-35 103.89-35 103.89-15.05Q103.89-10.9 104.59-8.08 105.29-5.25 106.69-3.75 108.09-2.25 109.84-1.63 111.59-1 114.04-1 116.49-1 118.24-1.63 119.99-2.25 121.39-3.75 122.79-5.25 123.49-8.08 124.19-10.9 124.19-15.05L124.19-15.05 124.19-33.5 106.54-33.5ZM136.64-35L136.64 0 135.14 0 135.14-35 136.64-35ZM150.44 0L150.44-1.5 165.94-1.5 148.04-32.45 148.04 0 146.54 0 146.54-35 148.29-35 166.99-2.65 166.99-35 168.49-35 168.49 0 150.44 0ZM196.34-19.8L196.34-18.3 181.49-18.3 196.79-33.5 179.89-33.5 179.89-1.5 199.29-1.5 199.29 0 178.39 0 178.39-35 200.44-35 185.14-19.8 196.34-19.8ZM202.98-35L227.98-35 227.98-33.5 216.23-33.5 216.23 0 214.73 0 214.73-33.5 202.98-33.5 202.98-35Z" opacity="1" transform="matrix(1,0,0,1,0,0)" fill="black" class="wordmark-text-0" id="SvgjsPath1322" stroke-width="5" stroke="black" stroke-linejoin="round"></path></svg></g></svg></g></svg></g></svg></g></svg></g></svg></g></svg></g></mask><g mask="url(#684aeb9f-56dd-430a-978a-41b3403ece50)"><g><path d="M318.186 10.579h-220.752v-10.579h235.916l-89.923 247.2-45.843-125.54-45.491 125.54-89.923-247.2h11.285l78.638 216.168 45.491-125.54 45.843 125.54z" fill="black" fill-rule="nonzero" stroke="none" stroke-width="1" stroke-linecap="butt" stroke-linejoin="miter" stroke-miterlimit="10" stroke-dasharray="" stroke-dashoffset="0" font-family="none" font-weight="none" font-size="none" text-anchor="none" style="mix-blend-mode: normal"></path></g></g><g transform="matrix(1,0,0,1,0,89.09954770622443)"><svg viewBox="0 0 395.52 69.00090458755115" height="69.00090458755115" width="395.52"><g><svg viewBox="0 0 395.52 69.00090458755115" height="69.00090458755115" width="395.52"><g><svg viewBox="0 0 395.52 69.00090458755115" height="69.00090458755115" width="395.52"><g><svg viewBox="0 0 395.52 69.00090458755115" height="69.00090458755115" width="395.52"><g id="SvgjsG1321"><svg viewBox="0 0 395.52 69.00090458755115" height="69.00090458755115" width="395.52" id="SvgjsSvg1320"><g><svg viewBox="0 0 395.52 69.00090458755115" height="69.00090458755115" width="395.52"><g transform="matrix(1,0,0,1,0,0)"><svg width="395.52" viewBox="-2.15 -38 233.13 41.5" height="69.00090458755115" data-palette-color="url(#6f9de062-2887-414b-be43-2e83111382c1)"><path d="M37.15-33.5L5.85-33.5 5.85-35 39.3-35 26.55 0.05 20.05-17.75 13.6 0.05 0.85-35 2.45-35 13.6-4.35 20.05-22.15 26.55-4.35 37.15-33.5ZM63.05-19.8L63.05-18.3 48.2-18.3 63.5-33.5 46.6-33.5 46.6-1.5 66-1.5 66 0 45.1 0 45.1-35 67.15-35 51.85-19.8 63.05-19.8ZM81.9 0L81.9 0 73.9 0 73.9-35 80-35Q86.6-35 89.95-32.58 93.3-30.15 93.3-25.75L93.3-25.75Q93.3-20.75 89.1-18.4L89.1-18.4Q95.2-16.1 95.2-9.75L95.2-9.75Q95.2-5.25 91.9-2.63 88.6 0 81.9 0ZM75.4-1.5L81.9-1.5Q84.25-1.5 86.2-1.88 88.15-2.25 89.92-3.13 91.7-4 92.7-5.7 93.7-7.4 93.7-9.75L93.7-9.75Q93.7-15.1 88.55-17L88.55-17 85.55-18.1 88.35-19.7Q91.8-21.6 91.8-25.75L91.8-25.75Q91.8-33.5 80-33.5L80-33.5 75.4-33.5 75.4-1.5ZM106.54-33.5L106.54-35 125.69-35 125.69-15.05Q125.69-7.05 122.94-3.28 120.19 0.5 114.04 0.5 107.89 0.5 105.14-3.28 102.39-7.05 102.39-15.05L102.39-15.05 102.39-35 103.89-35 103.89-15.05Q103.89-10.9 104.59-8.08 105.29-5.25 106.69-3.75 108.09-2.25 109.84-1.63 111.59-1 114.04-1 116.49-1 118.24-1.63 119.99-2.25 121.39-3.75 122.79-5.25 123.49-8.08 124.19-10.9 124.19-15.05L124.19-15.05 124.19-33.5 106.54-33.5ZM136.64-35L136.64 0 135.14 0 135.14-35 136.64-35ZM150.44 0L150.44-1.5 165.94-1.5 148.04-32.45 148.04 0 146.54 0 146.54-35 148.29-35 166.99-2.65 166.99-35 168.49-35 168.49 0 150.44 0ZM196.34-19.8L196.34-18.3 181.49-18.3 196.79-33.5 179.89-33.5 179.89-1.5 199.29-1.5 199.29 0 178.39 0 178.39-35 200.44-35 185.14-19.8 196.34-19.8ZM202.98-35L227.98-35 227.98-33.5 216.23-33.5 216.23 0 214.73 0 214.73-33.5 202.98-33.5 202.98-35Z" opacity="1" transform="matrix(1,0,0,1,0,0)" fill="black" class="wordmark-text-0" id="SvgjsPath1319"></path></svg></g></svg></g></svg></g></svg></g></svg></g></svg></g></svg></g></svg></g><defs><mask></mask></defs></svg><rect width="395.52" height="247.2" fill="black" stroke="none" visibility="hidden"></rect></g></mask></svg><rect width="395.52" height="247.2" fill="black" stroke="none" visibility="hidden"></rect></g></mask><linearGradient x1="0.054" x2="0.941" y1="0.5" y2="0.5" id="90ff3bf0-ffd8-47e9-9131-8ec53239fb3c"><stop stop-color="#864d25" offset="0"></stop><stop stop-color="#f1c4b3" offset="0.498"></stop><stop stop-color="#864d25" offset="1"></stop></linearGradient></svg><rect width="395.52" height="247.2" fill="none" stroke="none" visibility="hidden"></rect></g></svg></g></svg>
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
	

