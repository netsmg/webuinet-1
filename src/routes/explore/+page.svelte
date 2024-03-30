<!-- aggregator -->
	<section class="section section--first">
		<!-- section head -->
		<div class="section__head">
			<div class="container">
				<div class="row">
					<!-- breadcrumb -->
					<div class="col-12">
						<ul class="breadcrumbs">
							<li class="breadcrumbs__item"><a href="index/">Home</a></li>
							<li class="breadcrumbs__item breadcrumbs__item--active">Aggregator</li>
						</ul>
					</div>
					<!-- end breadcrumb -->

					<!-- section title -->
					<div class="col-12">
						<div class="section__title section__title--left section__title--page">
							<h1>GameFi Aggregator</h1>
						</div>
					</div>
					<!-- end section title -->
				</div>
			</div>

			<!-- bg animation -->
			<div id="canvas2" class="section__canvas"></div>
			<!-- end bg animation -->
		</div>
		<!-- end section head -->

		<!-- filter -->
		<div class="filter">
			<div class="container">
				<div class="row">
					<div class="col-12">
						<div class="filter__content">
							<form action="#" class="filter__search">
								<input type="text" placeholder="Search...">
								<button type="button" aria-label="Search"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M21.71,20.29,18,16.61A9,9,0,1,0,16.61,18l3.68,3.68a1,1,0,0,0,1.42,0A1,1,0,0,0,21.71,20.29ZM11,18a7,7,0,1,1,7-7A7,7,0,0,1,11,18Z"/></svg></button>
							</form>

							<div class="filter__wrap">
								<select class="filter__select" name="blockchain" id="filter__blockchain">
									<option value="0">All blockchains</option>
									<option value="1">Avalanche</option>
									<option value="2">Binance</option>
									<option value="3">Bitcoin</option>
									<option value="4">Cardano</option>
									<option value="5">Ethereum</option>
									<option value="6">Flow</option>
									<option value="7">Harmony</option>
									<option value="8">Litecoin</option>
									<option value="9">Near</option>
									<option value="10">NEO</option>
									<option value="11">Other</option>
								</select>

								<select class="filter__select" name="devices" id="filter__devices">
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

								<select class="filter__select" name="status" id="filter__status">
									<option value="0">Public status</option>
									<option value="1">Alpha</option>
									<option value="2">Beta</option>
									<option value="3">Cancelled</option>
									<option value="4">Development</option>
									<option value="5">Live</option>
									<option value="6">Presale</option>
								</select>
							</div>

							<button class="filter__menu" type="button"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M19,2H5A3,3,0,0,0,2,5V6.17a3,3,0,0,0,.25,1.2l0,.06a2.81,2.81,0,0,0,.59.86L9,14.41V21a1,1,0,0,0,.47.85A1,1,0,0,0,10,22a1,1,0,0,0,.45-.11l4-2A1,1,0,0,0,15,19V14.41l6.12-6.12a2.81,2.81,0,0,0,.59-.86l0-.06A3,3,0,0,0,22,6.17V5A3,3,0,0,0,19,2ZM13.29,13.29A1,1,0,0,0,13,14v4.38l-2,1V14a1,1,0,0,0-.29-.71L5.41,8H18.59ZM20,6H4V5A1,1,0,0,1,5,4H19a1,1,0,0,1,1,1Z"></path></svg>Filter</button>

							<span class="filter__amount">Showing 12 of 169</span>
						</div>
					</div>
				</div>
			</div>
		</div>
		<!-- end filter -->

		<!-- games -->
		<div class="container">
			<div class="row">
				<!-- game -->
				<div class="col-12 col-md-6 col-xl-4">
					<div class="game">
						<div class="game__head">
							<div class="game__cover">
								<img src="https://aurora.volkovdesign.com/img/games/1.png" alt="">
							</div>

							<div class="game__title">
								<h3 class="game__name">
									<a href="game/">Tank Metaverse</a>
								</h3>
								<span class="game__blockchain">
									Blockchains
									<img src="https://aurora.volkovdesign.com/img/blockchain/1.png" alt="BNB" data-bs-toggle="tooltip" data-bs-placement="bottom" data-bs-title="BNB">
									<img src="https://aurora.volkovdesign.com/img/blockchain/2.png" alt="Avalanche" data-bs-toggle="tooltip" data-bs-placement="bottom" data-bs-title="Avalanche">
								</span>
							</div>
						</div>

						<p class="game__description">Live out your wildest cowboy fantasies in the untamed wilderness of the American West, facing off against bandits and outlaws.</p>

						<ul class="game__list">
							<li>
								Devices <span>Web, Android, IOS</span>
							</li>
							<li>
								Free to play <span class="required">NFT Required</span>
							</li>
							<li>
								Play to earn <span class="required">Crypto</span>
							</li>
							<li>
								Status <span class="process">Presale</span>
							</li>
						</ul>

						<a href="game/" class="game__more"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M17.92,11.62a1,1,0,0,0-.21-.33l-5-5a1,1,0,0,0-1.42,1.42L14.59,11H7a1,1,0,0,0,0,2h7.59l-3.3,3.29a1,1,0,0,0,0,1.42,1,1,0,0,0,1.42,0l5-5a1,1,0,0,0,.21-.33A1,1,0,0,0,17.92,11.62Z"/></svg></a>
					</div>
				</div>
				<!-- end game -->

				<!-- game -->
				<div class="col-12 col-md-6 col-xl-4">
					<div class="game">
						<div class="game__head">
							<div class="game__cover">
								<img src="https://aurora.volkovdesign.com/img/games/2.png" alt="">
							</div>

							<div class="game__title">
								<h3 class="game__name">
									<a href="game/">Synergy Land</a>
								</h3>
								<span class="game__blockchain">
									Blockchain
									<img src="https://aurora.volkovdesign.com/img/blockchain/4.png" alt="Flow" data-bs-toggle="tooltip" data-bs-placement="bottom" data-bs-title="Flow">
								</span>
							</div>
						</div>

						<p class="game__description">Trek through the lush jungles of a tropical paradise, encountering exotic wildlife and uncovering hidden treasures.</p>

						<ul class="game__list">
							<li>
								Devices <span>Windows, MAC, Linux</span>
							</li>
							<li>
								Free to play <span class="true">Yes</span>
							</li>
							<li>
								Play to earn <span class="required">NFT & Crypto</span>
							</li>
							<li>
								Status <span class="true">Live</span>
							</li>
						</ul>

						<a href="game/" class="game__more"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M17.92,11.62a1,1,0,0,0-.21-.33l-5-5a1,1,0,0,0-1.42,1.42L14.59,11H7a1,1,0,0,0,0,2h7.59l-3.3,3.29a1,1,0,0,0,0,1.42,1,1,0,0,0,1.42,0l5-5a1,1,0,0,0,.21-.33A1,1,0,0,0,17.92,11.62Z"/></svg></a>
					</div>
				</div>
				<!-- end game -->

				<!-- game -->
				<div class="col-12 col-md-6 col-xl-4">
					<div class="game">
						<div class="game__head">
							<div class="game__cover">
								<img src="https://aurora.volkovdesign.com/img/games/3.png" alt="">
							</div>

							<div class="game__title">
								<h3 class="game__name">
									<a href="game/">Space Falcon</a>
								</h3>
								<span class="game__blockchain">
									Blockchains
									<img src="https://aurora.volkovdesign.com/img/blockchain/3.png" alt="Ethereum" data-bs-toggle="tooltip" data-bs-placement="bottom" data-bs-title="Ethereum">
									<img src="https://aurora.volkovdesign.com/img/blockchain/5.png" alt="Hive" data-bs-toggle="tooltip" data-bs-placement="bottom" data-bs-title="Hive">
								</span>
							</div>
						</div>

						<p class="game__description">Battle against other dragon riders in a high-flying arena, using skill and strategy to come out on top.</p>

						<ul class="game__list">
							<li>
								Devices <span>Android, IOS, Windows, MAC</span>
							</li>
							<li>
								Free to play <span class="true">Yes</span>
							</li>
							<li>
								Play to earn <span class="required">NFT</span>
							</li>
							<li>
								Status <span class="process">Alpha</span>
							</li>
						</ul>

						<a href="game/" class="game__more"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M17.92,11.62a1,1,0,0,0-.21-.33l-5-5a1,1,0,0,0-1.42,1.42L14.59,11H7a1,1,0,0,0,0,2h7.59l-3.3,3.29a1,1,0,0,0,0,1.42,1,1,0,0,0,1.42,0l5-5a1,1,0,0,0,.21-.33A1,1,0,0,0,17.92,11.62Z"/></svg></a>
					</div>
				</div>
				<!-- end game -->

				<!-- game -->
				<div class="col-12 col-md-6 col-xl-4">
					<div class="game">
						<div class="game__head">
							<div class="game__cover">
								<img src="https://aurora.volkovdesign.com/img/games/4.png" alt="">
							</div>

							<div class="game__title">
								<h3 class="game__name">
									<a href="game/">Battle Arena</a>
								</h3>
								<span class="game__blockchain">
									Blockchain
									<img src="https://aurora.volkovdesign.com/img/blockchain/6.png" alt="Polygon" data-bs-toggle="tooltip" data-bs-placement="bottom" data-bs-title="Polygon">
								</span>
							</div>
						</div>

						<p class="game__description">Galactic Rift is a multiplayer online battle arena game set in a sci-fi universe, where players battle for control of the galaxy using advanced spacecraft and strategic tactics.</p>

						<ul class="game__list">
							<li>
								Devices <span>Android, Windows</span>
							</li>
							<li>
								Free to play <span class="true">Yes</span>
							</li>
							<li>
								Play to earn <span class="required">NFT & Crypto</span>
							</li>
							<li>
								Status <span class="true">Live</span>
							</li>
						</ul>

						<a href="game/" class="game__more"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M17.92,11.62a1,1,0,0,0-.21-.33l-5-5a1,1,0,0,0-1.42,1.42L14.59,11H7a1,1,0,0,0,0,2h7.59l-3.3,3.29a1,1,0,0,0,0,1.42,1,1,0,0,0,1.42,0l5-5a1,1,0,0,0,.21-.33A1,1,0,0,0,17.92,11.62Z"/></svg></a>
					</div>
				</div>
				<!-- end game -->

				<!-- game -->
				<div class="col-12 col-md-6 col-xl-4">
					<div class="game">
						<div class="game__head">
							<div class="game__cover">
								<img src="https://aurora.volkovdesign.com/img/games/5.png" alt="">
							</div>

							<div class="game__title">
								<h3 class="game__name">
									<a href="game/">Open Era</a>
								</h3>
								<span class="game__blockchain">
									Blockchains
									<img src="https://aurora.volkovdesign.com/img/blockchain/3.png" alt="Ethereum" data-bs-toggle="tooltip" data-bs-placement="bottom" data-bs-title="Ethereum">
									<img src="https://aurora.volkovdesign.com/img/blockchain/7.png" alt="Solana" data-bs-toggle="tooltip" data-bs-placement="bottom" data-bs-title="Solana">
								</span>
							</div>
						</div>

						<p class="game__description">Embark on a time-traveling adventure to stop an evil organization from altering history.</p>

						<ul class="game__list">
							<li>
								Devices <span>Web, Android, IOS</span>
							</li>
							<li>
								Free to play <span class="required">NFT Required</span>
							</li>
							<li>
								Play to earn <span class="required">Crypto</span>
							</li>
							<li>
								Status <span class="process">Beta</span>
							</li>
						</ul>

						<a href="game/" class="game__more"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M17.92,11.62a1,1,0,0,0-.21-.33l-5-5a1,1,0,0,0-1.42,1.42L14.59,11H7a1,1,0,0,0,0,2h7.59l-3.3,3.29a1,1,0,0,0,0,1.42,1,1,0,0,0,1.42,0l5-5a1,1,0,0,0,.21-.33A1,1,0,0,0,17.92,11.62Z"/></svg></a>
					</div>
				</div>
				<!-- end game -->

				<!-- game -->
				<div class="col-12 col-md-6 col-xl-4">
					<div class="game">
						<div class="game__head">
							<div class="game__cover">
								<img src="https://aurora.volkovdesign.com/img/games/6.png" alt="">
							</div>

							<div class="game__title">
								<h3 class="game__name">
									<a href="game/">Immortal Arena</a>
								</h3>
								<span class="game__blockchain">
									Blockchains
									<img src="https://aurora.volkovdesign.com/img/blockchain/1.png" alt="BNB" data-bs-toggle="tooltip" data-bs-placement="bottom" data-bs-title="BNB">
									<img src="https://aurora.volkovdesign.com/img/blockchain/4.png" alt="Flow" data-bs-toggle="tooltip" data-bs-placement="bottom" data-bs-title="Flow">
								</span>
							</div>
						</div>

						<p class="game__description">Build and manage your own interstellar empire, competing against other players for domination of the galaxy.</p>

						<ul class="game__list">
							<li>
								Devices <span>Web</span>
							</li>
							<li>
								Free to play <span class="true">Yes</span>
							</li>
							<li>
								Play to earn <span class="required">NFT</span>
							</li>
							<li>
								Status <span class="process">Development</span>
							</li>
						</ul>

						<a href="game/" class="game__more"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M17.92,11.62a1,1,0,0,0-.21-.33l-5-5a1,1,0,0,0-1.42,1.42L14.59,11H7a1,1,0,0,0,0,2h7.59l-3.3,3.29a1,1,0,0,0,0,1.42,1,1,0,0,0,1.42,0l5-5a1,1,0,0,0,.21-.33A1,1,0,0,0,17.92,11.62Z"/></svg></a>
					</div>
				</div>
				<!-- end game -->

				<!-- game -->
				<div class="col-12 col-md-6 col-xl-4">
					<div class="game">
						<div class="game__head">
							<div class="game__cover">
								<img src="https://aurora.volkovdesign.com/img/games/7.png" alt="">
							</div>

							<div class="game__title">
								<h3 class="game__name">
									<a href="game/">Monster NFT</a>
								</h3>
								<span class="game__blockchain">
									Blockchains
									<img src="https://aurora.volkovdesign.com/img/blockchain/1.png" alt="BNB" data-bs-toggle="tooltip" data-bs-placement="bottom" data-bs-title="BNB">
									<img src="https://aurora.volkovdesign.com/img/blockchain/7.png" alt="Solana" data-bs-toggle="tooltip" data-bs-placement="bottom" data-bs-title="Solana">
								</span>
							</div>
						</div>

						<p class="game__description">Explore deep caverns filled with glittering gemstones and dangerous creatures, all while searching for hidden treasures.</p>

						<ul class="game__list">
							<li>
								Devices <span>Web, Android, IOS</span>
							</li>
							<li>
								Free to play <span class="required">NFT Required</span>
							</li>
							<li>
								Play to earn <span class="required">Crypto</span>
							</li>
							<li>
								Status <span class="process">Presale</span>
							</li>
						</ul>

						<a href="game/" class="game__more"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M17.92,11.62a1,1,0,0,0-.21-.33l-5-5a1,1,0,0,0-1.42,1.42L14.59,11H7a1,1,0,0,0,0,2h7.59l-3.3,3.29a1,1,0,0,0,0,1.42,1,1,0,0,0,1.42,0l5-5a1,1,0,0,0,.21-.33A1,1,0,0,0,17.92,11.62Z"/></svg></a>
					</div>
				</div>
				<!-- end game -->

				<!-- game -->
				<div class="col-12 col-md-6 col-xl-4">
					<div class="game">
						<div class="game__head">
							<div class="game__cover">
								<img src="https://aurora.volkovdesign.com/img/games/8.png" alt="">
							</div>

							<div class="game__title">
								<h3 class="game__name">
									<a href="game/">X World Games</a>
								</h3>
								<span class="game__blockchain">
									Blockchain
									<img src="https://aurora.volkovdesign.com/img/blockchain/5.png" alt="Hive" data-bs-toggle="tooltip" data-bs-placement="bottom" data-bs-title="Hive">
								</span>
							</div>
						</div>

						<p class="game__description">Raise and train your own dragons, then battle against other dragon trainers for supremacy.</p>

						<ul class="game__list">
							<li>
								Devices <span>Windows, MAC, Linux</span>
							</li>
							<li>
								Free to play <span class="true">Yes</span>
							</li>
							<li>
								Play to earn <span class="required">NFT & Crypto</span>
							</li>
							<li>
								Status <span class="true">Live</span>
							</li>
						</ul>

						<a href="game/" class="game__more"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M17.92,11.62a1,1,0,0,0-.21-.33l-5-5a1,1,0,0,0-1.42,1.42L14.59,11H7a1,1,0,0,0,0,2h7.59l-3.3,3.29a1,1,0,0,0,0,1.42,1,1,0,0,0,1.42,0l5-5a1,1,0,0,0,.21-.33A1,1,0,0,0,17.92,11.62Z"/></svg></a>
					</div>
				</div>
				<!-- end game -->

				<!-- game -->
				<div class="col-12 col-md-6 col-xl-4">
					<div class="game">
						<div class="game__head">
							<div class="game__cover">
								<img src="https://aurora.volkovdesign.com/img/games/9.png" alt="">
							</div>

							<div class="game__title">
								<h3 class="game__name">
									<a href="game/">Gunstar Metaverse</a>
								</h3>
								<span class="game__blockchain">
									Blockchains
									<img src="https://aurora.volkovdesign.com/img/blockchain/4.png" alt="Flow" data-bs-toggle="tooltip" data-bs-placement="bottom" data-bs-title="Flow">
									<img src="https://aurora.volkovdesign.com/img/blockchain/6.png" alt="Polygon" data-bs-toggle="tooltip" data-bs-placement="bottom" data-bs-title="Polygon">
								</span>
							</div>
						</div>

						<p class="game__description">Journey through a mystical world, bonding with powerful spirits to unlock new abilities and defeat dark forces.</p>

						<ul class="game__list">
							<li>
								Devices <span>Android, IOS, Windows, MAC</span>
							</li>
							<li>
								Free to play <span class="true">Yes</span>
							</li>
							<li>
								Play to earn <span class="required">NFT</span>
							</li>
							<li>
								Status <span class="process">Alpha</span>
							</li>
						</ul>

						<a href="game/" class="game__more"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M17.92,11.62a1,1,0,0,0-.21-.33l-5-5a1,1,0,0,0-1.42,1.42L14.59,11H7a1,1,0,0,0,0,2h7.59l-3.3,3.29a1,1,0,0,0,0,1.42,1,1,0,0,0,1.42,0l5-5a1,1,0,0,0,.21-.33A1,1,0,0,0,17.92,11.62Z"/></svg></a>
					</div>
				</div>
				<!-- end game -->

				<!-- game -->
				<div class="col-12 col-md-6 col-xl-4">
					<div class="game">
						<div class="game__head">
							<div class="game__cover">
								<img src="https://aurora.volkovdesign.com/img/games/10.png" alt="">
							</div>

							<div class="game__title">
								<h3 class="game__name">
									<a href="game/">Titan Hunters</a>
								</h3>
								<span class="game__blockchain">
									Blockchain
									<img src="https://aurora.volkovdesign.com/img/blockchain/1.png" alt="BNB" data-bs-toggle="tooltip" data-bs-placement="bottom" data-bs-title="BNB">
								</span>
							</div>
						</div>

						<p class="game__description">Race through futuristic cityscapes at breakneck speeds, dodging obstacles and outmaneuvering your opponents.</p>

						<ul class="game__list">
							<li>
								Devices <span>Android, Windows</span>
							</li>
							<li>
								Free to play <span class="true">Yes</span>
							</li>
							<li>
								Play to earn <span class="required">NFT & Crypto</span>
							</li>
							<li>
								Status <span class="true">Live</span>
							</li>
						</ul>

						<a href="game/" class="game__more"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M17.92,11.62a1,1,0,0,0-.21-.33l-5-5a1,1,0,0,0-1.42,1.42L14.59,11H7a1,1,0,0,0,0,2h7.59l-3.3,3.29a1,1,0,0,0,0,1.42,1,1,0,0,0,1.42,0l5-5a1,1,0,0,0,.21-.33A1,1,0,0,0,17.92,11.62Z"/></svg></a>
					</div>
				</div>
				<!-- end game -->

				<!-- game -->
				<div class="col-12 col-md-6 col-xl-4">
					<div class="game">
						<div class="game__head">
							<div class="game__cover">
								<img src="https://aurora.volkovdesign.com/img/games/11.png" alt="">
							</div>

							<div class="game__title">
								<h3 class="game__name">
									<a href="game/">MetaSoccer</a>
								</h3>
								<span class="game__blockchain">
									Blockchains
									<img src="https://aurora.volkovdesign.com/img/blockchain/4.png" alt="Flow" data-bs-toggle="tooltip" data-bs-placement="bottom" data-bs-title="Flow">
									<img src="https://aurora.volkovdesign.com/img/blockchain/5.png" alt="Hive" data-bs-toggle="tooltip" data-bs-placement="bottom" data-bs-title="Hive">
								</span>
							</div>
						</div>

						<p class="game__description">Explore a vast, procedurally generated universe filled with alien worlds, ancient ruins, and hostile forces.</p>

						<ul class="game__list">
							<li>
								Devices <span>Web, Android, IOS</span>
							</li>
							<li>
								Free to play <span class="required">NFT Required</span>
							</li>
							<li>
								Play to earn <span class="required">Crypto</span>
							</li>
							<li>
								Status <span class="process">Beta</span>
							</li>
						</ul>

						<a href="game/" class="game__more"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M17.92,11.62a1,1,0,0,0-.21-.33l-5-5a1,1,0,0,0-1.42,1.42L14.59,11H7a1,1,0,0,0,0,2h7.59l-3.3,3.29a1,1,0,0,0,0,1.42,1,1,0,0,0,1.42,0l5-5a1,1,0,0,0,.21-.33A1,1,0,0,0,17.92,11.62Z"/></svg></a>
					</div>
				</div>
				<!-- end game -->

				<!-- game -->
				<div class="col-12 col-md-6 col-xl-4">
					<div class="game">
						<div class="game__head">
							<div class="game__cover">
								<img src="https://aurora.volkovdesign.com/img/games/12.png" alt="">
							</div>

							<div class="game__title">
								<h3 class="game__name">
									<a href="game/">Realms Of Ethernity</a>
								</h3>
								<span class="game__blockchain">
									Blockchains
									<img src="https://aurora.volkovdesign.com/img/blockchain/2.png" alt="Avalanche" data-bs-toggle="tooltip" data-bs-placement="bottom" data-bs-title="Avalanche">
									<img src="https://aurora.volkovdesign.com/img/blockchain/6.png" alt="Polygon" data-bs-toggle="tooltip" data-bs-placement="bottom" data-bs-title="Polygon">
								</span>
							</div>
						</div>

						<p class="game__description">Soar through the clouds on a magical airship, facing off against sky pirates and other aerial threats.</p>

						<ul class="game__list">
							<li>
								Devices <span>Web</span>
							</li>
							<li>
								Free to play <span class="true">Yes</span>
							</li>
							<li>
								Play to earn <span class="required">NFT</span>
							</li>
							<li>
								Status <span class="process">Development</span>
							</li>
						</ul>

						<a href="game/" class="game__more"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M17.92,11.62a1,1,0,0,0-.21-.33l-5-5a1,1,0,0,0-1.42,1.42L14.59,11H7a1,1,0,0,0,0,2h7.59l-3.3,3.29a1,1,0,0,0,0,1.42,1,1,0,0,0,1.42,0l5-5a1,1,0,0,0,.21-.33A1,1,0,0,0,17.92,11.62Z"/></svg></a>
					</div>
				</div>
				<!-- end game -->
			</div>

			<!-- paginator -->
			<div class="row">
				<div class="col-12">
					<div class="paginator">
						<span class="paginator__pages">12 from 169</span>

						<ul class="paginator__list-mobile">
							<li>
								<a href="/">
									<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M17,11H9.41l3.3-3.29a1,1,0,1,0-1.42-1.42l-5,5a1,1,0,0,0-.21.33,1,1,0,0,0,0,.76,1,1,0,0,0,.21.33l5,5a1,1,0,0,0,1.42,0,1,1,0,0,0,0-1.42L9.41,13H17a1,1,0,0,0,0-2Z"/></svg>
									<span>Prev</span>
								</a>
							</li>
							<li>
								<a href="/">
									<span>Next</span>
									<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M17.92,11.62a1,1,0,0,0-.21-.33l-5-5a1,1,0,0,0-1.42,1.42L14.59,11H7a1,1,0,0,0,0,2h7.59l-3.3,3.29a1,1,0,0,0,0,1.42,1,1,0,0,0,1.42,0l5-5a1,1,0,0,0,.21-.33A1,1,0,0,0,17.92,11.62Z"/></svg>
								</a>
							</li>
						</ul>

						<ul class="paginator__list">
							<li>
								<a href="/"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M17,11H9.41l3.3-3.29a1,1,0,1,0-1.42-1.42l-5,5a1,1,0,0,0-.21.33,1,1,0,0,0,0,.76,1,1,0,0,0,.21.33l5,5a1,1,0,0,0,1.42,0,1,1,0,0,0,0-1.42L9.41,13H17a1,1,0,0,0,0-2Z"/></svg></a>
							</li>
							<li class="active"><a href="/">1</a></li>
							<li><a href="/">2</a></li>
							<li><a href="/">3</a></li>
							<li><a href="/">4</a></li>
							<li><span>...</span></li>
							<li><a href="/">18</a></li>
							<li><a href="/">19</a></li>
							<li>
								<a href="/"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M17.92,11.62a1,1,0,0,0-.21-.33l-5-5a1,1,0,0,0-1.42,1.42L14.59,11H7a1,1,0,0,0,0,2h7.59l-3.3,3.29a1,1,0,0,0,0,1.42,1,1,0,0,0,1.42,0l5-5a1,1,0,0,0,.21-.33A1,1,0,0,0,17.92,11.62Z"/></svg></a>
							</li>
						</ul>
					</div>
				</div>
			</div>
			<!-- end paginator -->
		</div>
		<!-- end games -->
	</section>
	<!-- end aggregator -->
