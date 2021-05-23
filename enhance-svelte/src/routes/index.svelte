<script>
	import successkid from 'images/successkid.jpg';

	function handleRoute(auth) {
		window.location.href = 'setup?auth=' + auth
	}

</script>

<style>

	img {
		width: 100%;
		max-width: 400px;
	}

	p {
		margin: 1em auto;
	}

	.enhance_header_container {
		display: inline-flex; justify-content: center; align-items: center; width: 100%; flex-direction: column;
	}

	.trello_img {
		width: 4rem; margin: 1rem; margin-bottom: -0.75rem; align-self: flex-start; 
	}

	.enhance_title {
		display: inline-block;
		font-size: 3em; margin: 0; margin-right: 1rem
	}

	.github_img {
		width: 4rem; align-self: flex-end;
		margin-top: 1.5rem;
	}

	.catchline {
		text-align: left;
		font-size: 1.25em;
	}

	.test {
		bottom: 45%;
		position: absolute;
	}


	.lower_section {
		width: 100%;
		background-color: #10669b;
		position: absolute;
		height: 46%;
		bottom: 0;
	}

	.lower_section_part {
		width: 100%;
		display: flex;
		align-items: center;
	}

	.white_bar {
		height: 4rem;
		width: 4px;
		background-color: white;
		display: inline-block;
		border-top-right-radius: 25px;;
		border-bottom-right-radius: 25px;
	}

	.lower_section_part_text {
		text-align: left;
		margin-left: 7%;
		font-size: 1.5rem;
	}

	.authenticate_box {
		display: flex;
		flex-direction: column;
		width: 100%;
		justify-content: center;
		align-items: center;
		margin-top: 2rem;
	}
	.purple_auth_bar {
		width: 55%;
		height: 5px;
		display: inline-block;
		background-color: #b193ff;
		border-radius: 50px;
		margin-top: 0.5rem;
	}

	.blue_auth_bar {
		width: 35%;
		height: 5px;
		display: inline-block;
		background-color: #6d93ff;
		border-radius: 50px;
		margin-top: 0.5rem;
	}

	.authenticate {
		margin-top: 10%;
	}

	.authenticate_box:hover .purple_auth_bar {
		-webkit-box-shadow: 0px 0px 15px -1px #B193FF; 
		box-shadow: 0px 0px 15px -1px #B193FF;
	}

	.authenticate_box:hover, .blue_auth_bar {
		-webkit-box-shadow: 0px 0px 15px -1px #6d93ff; 
		box-shadow: 0px 0px 15px -1px #6d93ff;
	}

	.authenticate_box:hover .authenticate_text {
		-webkit-text-shadow: 0px 0px  5px white;
		text-shadow: 0px 0px  5px white;

	}

</style>

<svelte:head>
	<title>Sapper project template</title>
</svelte:head>

<div class="enhance_header_container">
	<img class="trello_img" src="../images/trello.svg" alt="trello">
	<div style="    display: flex;
	width: 100%;
    justify-content: flex-end;
    align-content: center;
    flex-direction: row;
	align-items: center;
">
		<img style="width: 4rem; height: 100%; display: inline-block;" src="../images/noslogan.png" alt="enhance logo">
		<p class="enhance_title">Enhance</p>
	</div>
	<img class="github_img" src="../images/github.svg" alt="github">
	
	<p class="catchline">Get ready for a new way to<br>
		manage your awesome projects.</p>

			<svg xmlns="http://www.w3.org/2000/svg"  class="test" viewBox="0 0 1440 320">
				<path fill="#10669b" fill-opacity="1" d="M0,0L60,42.7C120,85,240,171,360,197.3C480,224,600,192,720,170.7C840,149,960,139,1080,149.3C1200,160,1320,192,1380,208L1440,224L1440,320L1380,320C1320,320,1200,320,1080,320C960,320,840,320,720,320C600,320,480,320,360,320C240,320,120,320,60,320L0,320Z"></path>
			  </svg>
			<div class="lower_section">
				<div class="lower_section_part">
					<div class="white_bar"></div>
					<div class="lower_section_part_text">Login to continue</div>
				</div>

				<div on:click="{() => handleRoute('github')}" class="authenticate">
					<div class="authenticate_box">
						<div class="authenticate_text">Authenticate with GitHub</div>
						<div class="purple_auth_bar"></div>
						<div class="blue_auth_bar"></div>
					</div>

					<div on:click="{() => handleRoute('google')}" class="authenticate_box">
							<div class="authenticate_text">Authenticate with Google</div>
							<div class="purple_auth_bar"></div>
							<div class="blue_auth_bar"></div>
					</div>
				</div>

			</div>

</div>