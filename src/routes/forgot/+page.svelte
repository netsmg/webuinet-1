<script>
  import { getAuth, sendPasswordResetEmail } from 'firebase/auth'; 
  import { app } from '../../firebase';
  
  const auth = getAuth(app);
  let email = ''; // Define email variable

  async function sendResetEmail() {
    const email = document.getElementById('emailInput').value.trim(); // Retrieve email value directly
    if (!email) {
      console.error('Email is required.');
      return;
    }

    try {
      // Send password reset email
      await sendPasswordResetEmail(auth, email); // Corrected function name
      console.log('Password reset email sent successfully.');
      // Display success message
      document.getElementById('successMessage').style.display = 'block';
    } catch (error) {
      console.error('Error sending password reset email:', error);
      // Display error message to the user
    }
  }
</script>

<!-- page wrap -->
<div class="section section--content">
  <div class="section__content">
    <!-- form -->
    <form class="form form--content" on:submit|preventDefault={sendResetEmail}> <!-- Added preventDefault to prevent form submission -->
      <div class="form__logo-wrap">
        <a href="/" class="form__logo">
          <img src="/logo.svg" alt="Logo">
        </a>
        <span class="form__tagline">Reset your password</span>
      </div>

      <div class="form__group">
        <input type="text" class="form__input" id="emailInput" placeholder="Email">
      </div>
      <div id="successMessage" class="form__text form__text--success form__text--center" style="display: none;">Password reset email sent successfully.</div>

      <div class="form__group form__group--checkbox">
        <input id="remember" name="remember" type="checkbox">
        <label for="remember">I agree to the <a href="privacy">Privacy Policy</a></label>
      </div>
      
      <button class="form__btn" type="submit">Send</button>

      <span class="form__text form__text--center">We will send a password reset Email</span>
    </form>
    <!-- end form -->
  </div>

  <!-- bg animation -->
  <div id="canvas2" class="section__canvas"></div>
  <!-- end bg animation -->
</div>
<!-- end page wrap -->
