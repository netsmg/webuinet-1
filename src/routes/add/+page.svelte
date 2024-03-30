<section class="section section--first">
		<!-- section head -->
		<div class="section__article-head">
			<div class="container">
				<div class="row">
<!-- bg animation -->
			<div id="canvas2" class="section__canvas"></div>
			<!-- end bg animation -->
		</div>
		<!-- end section head -->

		<!-- form -->
		<div class="container">
			<div class="row">
				<div class="col-12">
					<form class="form form--big" action="#">
						<div class="row">
							<div class="col-12 col-md-6">
								<div class="form__group">
									<label for="name" class="form__label">Name</label>
									<input id="name" type="text" name="name" class="form__input">
								</div>
							</div>

							<div class="col-12 col-md-6">
								<div class="form__group">
									<label for="teaser" class="form__label">Teaser</label>
									<input id="teaser" type="text" name="teaser" class="form__input">
								</div>
							</div>

							<div class="col-12">
								<div class="form__group">
									<label for="description" class="form__label">Description</label>
									<textarea id="description" name="description" class="form__textarea"></textarea>
								</div>
							</div>

							<div class="col-12 col-lg-4">
								<div class="form__group">
									<label for="form__gallery-upload" class="form__label">Main image</label>
									<div class="form__gallery">
										<label id="gallery1" for="form__gallery-upload">Upload cover</label>
										<input data-name="#gallery1" id="form__gallery-upload" name="gallery" class="form__gallery-upload" type="file" accept=".png, .jpg, .jpeg" multiple>
									</div>
								</div>
							</div>

							<div class="col-12 col-lg-4">
								<div class="form__group">
									<label for="trailer" class="form__label">Game video (Youtube link)</label>
									<input id="trailer" type="text" name="trailer" class="form__input form__input--link" placeholder="https://www.youtube.com/watch?v=xxxxxx">
								</div>
							</div>

							<div class="col-12 col-lg-4">
								<div class="form__group">
									<label for="form__status" class="form__label">Public status</label>
									<select id="form__status" class="form__select" name="form__status">
										<option value="0">Alpha</option>
										<option value="1">Beta</option>
										<option value="2">Cancelled</option>
										<option value="3">Development</option>
										<option value="4">Live</option>
										<option value="5">Presale</option>
									</select>
								</div>
							</div>

							<div class="col-12">
								<span class="form__line"></span>
							</div>

							<div class="col-12 col-lg-6">
								<div class="form__group">
									<label for="form__blockchain" class="form__label">Blockchain</label>
									<select id="form__blockchain" class="form__select" name="form__blockchain" multiple>
										<option value="0">Avalanche</option>
										<option value="1">Binance Smart Chain</option>
										<option value="2">Bitcoin</option>
										<option value="3">Cardano</option>
										<option value="4">Ethereum</option>
										<option value="5">Fantom</option>
										<option value="6">Flow</option>
										<option value="7">Harmony</option>
										<option value="8">Hive</option>
										<option value="9">Litecoin</option>
										<option value="10">Near</option>
										<option value="11">NEO</option>
										<option value="12">Polkadot</option>
										<option value="13">Polygon</option>
										<option value="14">Solana</option>
										<option value="15">Waves</option>
									</select>
								</div>
							</div>

							<div class="col-12 col-lg-6">
								<div class="form__group">
									<label for="form__devices" class="form__label">Devices</label>
									<select id="form__devices" class="form__select" name="form__devices" multiple>
										<option value="0">All devices</option>
										<option value="1">Android</option>
										<option value="2">IOS</option>
										<option value="3">Linux</option>
										<option value="4">MAC</option>
										<option value="5">Playstation</option>
										<option value="6">Web</option>
										<option value="7">Windows</option>
										<option value="8">XBOX</option>
									</select>
								</div>
							</div>

							<div class="col-12 col-lg-4">
								<div class="form__group">
									<label for="form__ftp" class="form__label">Free to play</label>
									<select id="form__ftp" class="form__select" name="form__ftp">
										<option value="0">Yes</option>
										<option value="1">NFT Required</option>
										<option value="2">Crypto Required</option>
										<option value="3">Game Required</option>
									</select>
								</div>
							</div>

							<div class="col-12 col-lg-4">
								<div class="form__group">
									<label for="form__pte" class="form__label">Play to earn</label>
									<select id="form__pte" class="form__select" name="form__pte">
										<option value="0">No</option>
										<option value="1">NFT</option>
										<option value="2">Crypto</option>
										<option value="3">NFT & Crypto</option>
									</select>
								</div>
							</div>

							<div class="col-12 col-lg-4">
								<div class="form__group">
									<label for="form__genres" class="form__label">Game genres</label>
									<select id="form__genres" class="form__select" name="form__genres" multiple>
										<option value="0">Action</option>
										<option value="1">Adventure</option>
										<option value="2">Arcade</option>
										<option value="3">Art</option>
										<option value="4">Battle-Royale</option>
										<option value="5">Board</option>
										<option value="6">Building</option>
										<option value="7">Card</option>
										<option value="8">Casual</option>
										<option value="9">Collectible</option>
										<option value="10">Dungeon</option>
										<option value="11">Educational</option>
										<option value="12">Escape</option>
										<option value="13">eSports</option>
										<option value="14">Fantasy</option>
										<option value="15">Fighting</option>
										<option value="16">Horror</option>
										<option value="17">Logic</option>
										<option value="18">Mining</option>
										<option value="19">MMO</option>
										<option value="20">MMORPG</option>
										<option value="21">MOBA</option>
										<option value="22">Move-To-Earn</option>
										<option value="23">Open-World</option>
										<option value="24">Platformer</option>
										<option value="25">PVP</option>
										<option value="26">Racing</option>
										<option value="27">RPG</option>
										<option value="28">Sci-Fi</option>
										<option value="29">Shooter</option>
										<option value="30">Simulation</option>
										<option value="31">Sports</option>
										<option value="32">Strategy</option>
										<option value="33">Survival</option>
										<option value="34">Tactical</option>
										<option value="35">Tower-Defense</option>
										<option value="36">Virtual-Reality</option>
										<option value="37">Virtual-World</option>
									</select>
								</div>
							</div>

							<div class="col-12">
								<span class="form__line"></span>
							</div>

							<div class="col-12 col-md-6 col-xl-4">
								<div class="form__group">
									<label for="website" class="form__label">Website</label>
									<input id="website" type="text" name="website" class="form__input form__input--link">
								</div>
							</div>
							<div class="col-12 col-md-6 col-xl-4">
								<div class="form__group">
									<label for="twitter" class="form__label">Twitter</label>
									<input id="twitter" type="text" name="twitter" class="form__input form__input--link">
								</div>
							</div>
							<div class="col-12 col-md-6 col-xl-4">
								<div class="form__group">
									<label for="discord" class="form__label">Discord</label>
									<input id="discord" type="text" name="discord" class="form__input form__input--link">
								</div>
							</div>
							<div class="col-12 col-md-6 col-xl-4">
								<div class="form__group">
									<label for="telegram" class="form__label">Telegram</label>
									<input id="telegram" type="text" name="telegram" class="form__input form__input--link">
								</div>
							</div>
							<div class="col-12 col-md-6 col-xl-4">
								<div class="form__group">
									<label for="youtube" class="form__label">Youtube</label>
									<input id="youtube" type="text" name="youtube" class="form__input form__input--link">
								</div>
							</div>
							<div class="col-12 col-md-6 col-xl-4">
								<div class="form__group">
									<label for="facebook" class="form__label">Facebook</label>
									<input id="facebook" type="text" name="facebook" class="form__input form__input--link">
								</div>
							</div>

							<div class="col-12">
								<span class="form__line"></span>
							</div>

							<div class="col-12 col-md-6">
								<div class="form__group">
									<label for="yourname" class="form__label">Your name</label>
									<input id="yourname" type="text" name="yourname" class="form__input">
								</div>
							</div>
							<div class="col-12 col-md-6">
								<div class="form__group">
									<label for="email" class="form__label">Email</label>
									<input id="email" type="text" name="email" class="form__input">
								</div>
							</div>
							<div class="col-12">
								<div class="form__group">
									<label for="contacts" class="form__label">Your other contacts</label>
									<textarea id="contacts" name="contacts" class="form__textarea"></textarea>
								</div>
							</div>

							<div class="col-12">
								<button type="button" class="form__btn form__btn--small">Submit</button>
							</div>
						</div>
					</form>
				</div>
			</div>
		</div>
		<!-- end form -->
	</section>
	<!-- end add game -->
