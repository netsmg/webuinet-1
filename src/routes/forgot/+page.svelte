<script>
  import { getAuth, sendPasswordResetEmail } from 'firebase/auth'; 
  import { app } from '../../firebase';
  
  const auth = getAuth(app);
  const emailInput = document.getElementById('emailInput');
  const successMessage = document.getElementById('successMessage');

  async function sendPasswordResetEmail() {
    const email = emailInput.value.trim();
    if (!email) {
      console.error('Email is required.');
      return;
    }

    try {
      // Send password reset email
      await sendPasswordResetEmail(auth, email);
      console.log('Password reset email sent successfully.');
      // Display success message
      successMessage.style.display = 'block';
    } catch (error) {
      console.error('Error sending password reset email:', error);
      // Display error message to the user
    }
  }

  const sendButton = document.querySelector('.form__btn');
  sendButton.addEventListener('click', sendPasswordResetEmail);
</script>



<!-- page wrap -->
	<div class="section section--content">
		<div class="section__content">
			<!-- form -->
			<form class="form form--content">
				<div class="form__logo-wrap">
					<a href="index.html" class="form__logo">
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
				
				<button class="form__btn" type="button">Send</button>

				<span class="form__text form__text--center">We will send a password reset Email</span>
			</form>
			<!-- end form -->
		</div>

		<!-- bg animation -->
		<div id="canvas2" class="section__canvas"></div>
		<!-- end bg animation -->
	</div>
	<!-- end page wrap -->

	<!-- JS -->
