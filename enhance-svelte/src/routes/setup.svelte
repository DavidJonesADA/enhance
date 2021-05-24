<svelte:head>
	<title>About</title>
</svelte:head>

<script>

	let t1 = 'Not Connected!'

	let t2 = 'Click here to sign in..'

	let trelloConnected = false

	let allowContinue = false;

	function changeConnect() {
		t1 = 'Connected as: david.jones@ada.ac.uk'
		t2 = ''
		trelloConnected = true;
	}

	let selectSrc = ''

	function handleRoute() {
		window.location.href = '/calendar'
	}

	function test() {
		document.getElementById('no1').style.background = 'none'
		document.getElementById('no2').style.background = 'none'
		document.getElementById('no3').style.background = 'none'
		selectSrc = document.getElementById(this.id + 'image').src
		this.style.background = '#ffa7a7'
	}

	let currentRep = ''

	let currentText = ''

	function openmodal() {
		currentRep = this.id + 'image'
		currentText = document.getElementById(this.id + 'text').innerText
		document.getElementById('modal').style.display = 'block'
	}

	function closemodal() {
		document.getElementById(currentRep).style.width = '15px'
		document.getElementById(currentRep).style.height = '15px'
		document.getElementById(currentRep).src = selectSrc || '../images/chrome_50Qf9Ziy8v.png'
		document.getElementById('modal').style.display = 'none'
	}
</script>

<div id="modal" style="width: 100vw; height: 100vh; position: absolute; display: none;">
	<div style="z-index: 3; position: absolute; width: 100%; height: 100vh; display: flex; align-items: center; justify-content: center;">
		<div style="text-align: center; width: 100%; margin: 2rem; height: 33%; background-color: #fbfbfb; border-radius: 0.25rem; color: #292929; font-size: 1.25em; ">
			<div style="margin-top: 0.5rem; margin-bottom: 0.5rem;">Please select your Trello Board</div>
			<div style="font-size: 0.85em; background-color: #84c6ff; display: inline-block; padding: 0.25rem; border-radius: 25px;">
				<div>
					GitHub Repo: {currentText}
				</div>
			</div>
			<div>
				<div id="no1" style="margin-top: 0.75rem; display: flex; justify-content: center; align-items: center; padding: 0.25rem;" on:click={test}>
					<img id="no1image" src="../images/chrome_lGoPS9sQw2.png" alt="trelloc1">
					<div style="font-size: 0.95rem; margin-left: 0.5rem;">Next-Js Board</div>
				</div>
				<div id="no2" style="margin-top: 0.75rem; display: flex; justify-content: center; align-items: center; padding: 0.25rem;" on:click={test}>
					<img id="no2image" src="../images/chrome_52qINqGVNK.png" alt="trelloc2">
					<div style="font-size: 0.95rem; margin-left: 0.5rem;">LastPass Board</div>
				</div>
				<div id="no3" style="margin-top: 0.75rem; display: flex; justify-content: center; align-items: center; padding: 0.25rem;" on:click={test}>
					<img id="no3image" src="../images/chrome_50Qf9Ziy8v.png" alt="trelloc3">
					<div style="font-size: 0.95rem; margin-left: 0.5rem;">Spotify-Fix Board</div>
				</div>
			</div>
			<div style="margin-top: 1rem; padding: 0.25rem; display: inline-block; border-radius: 2" on:click={closemodal}>
				Continue
			</div>
		</div>
	</div>

	<div style="position: absolute; width: 100vw; height: 100vh; background-color: #000000; opacity: 25%; z-index: 2; top: -15px;">

	</div>
</div>

<h1 class="setup_title">Awesome!</h1>

<div style="margin-top: 0.45rem; font-size: 2.5em; font-weight: 300; text-align: center;">Lets get you setup</div>

<div style="margin-top: 2.45rem; font-size: 1.5em; font-weight: 500; text-align: left; display: flex; align-items: center;">
	
	<div class="white_bar" style="margin-right: 0.5rem;">

	</div>
	<div>
		<div style="display: flex; align-items: center;">
			Authorize GitHub
			<img src="../images/connected.svg" style="margin-left: 0.5rem; width: 1.5rem; margin-top: 0.2rem;;" alt="Tick">

		</div>
		
		<div style="font-size: 0.75rem">Connected as: DavidJonesADA</div>
	</div>
	


</div>



<div style="margin-top: 2.45rem; margin-bottom: 2rem; font-size: 1.5em; font-weight: 500; text-align: left; display: flex; align-items: center;">
	
	<div class="white_bar" style="margin-right: 0.5rem;">

	</div>
	<div>
		<div style="display: flex; align-items: center; height: 31px;">
			Connect To Trello
			{#if !trelloConnected}
			<div class="lds-grid"><div></div><div></div><div></div><div></div><div></div><div></div><div></div><div></div><div></div></div>
			{:else}
			<img src="../images/connected.svg" style="margin-left: 0.5rem; width: 1.5rem; margin-top: 0.2rem;;" alt="Tick">
			{/if}
		</div>
		
		<div style="font-size: 0.75rem; display: flex;">
			
			<div style="margin-right: 0.5ch">
				{t1}
			</div>
			<div style="cursor: pointer; color: #84ff8e" on:click={changeConnect}>
				{t2}
			</div>
			</div>
	</div>

</div>

<img src="../images/searchghub.svg" alt="searchghub">

<div class="repos">
	<div style="font-size: 1.25em; text-align: center; margin-bottom: 1.25em">
		Please select your github repositories
	</div>

	<div id="rep1" class="rep rep1" on:click={openmodal}>
		<img src="../images/gitrep.svg" alt="gitrepo" style="max-height: 3em;">
		<div style="display: flex; flex-direction: column;">
			<div style="font-size: 1rem; min-width: 125px; display: flex; align-items: center;">DavidJonesAda/<img id="rep1image" class="repimage" style="margin-left: 0.25rem width: 0px; height: 0px;"  src="../images/chrome_lGoPS9sQw2.png" alt="testimage1"></div>
			<div id="rep1text" style="font-size: 0.75rem; margin-top: -0.35rem">spotify-old-version-fix</div>
		</div>
	</div>
	<div id="rep2" class="rep rep2" on:click={openmodal}>
		<img src="../images/gitrep.svg" alt="gitrepo" style="max-height: 3em;">
		<div style="display: flex; flex-direction: column;">
			<div style="font-size: 1rem; min-width: 125px; display: flex; align-items: center;">DavidJonesAda/<img id="rep2image" class="repimage"style="margin-left: 0.25rem width: 0px; height: 0px;" src="../images/chrome_lGoPS9sQw2.png" alt="testimage2"></div>

			<div id="rep2text" style="font-size: 0.75rem; margin-top: -0.35rem">next-js</div>
		</div>
	</div>
	<div id="rep3" class="rep rep3" on:click={openmodal}>
		<img src="../images/gitrep.svg" alt="gitrepo" style="max-height: 3em;">
		<div style="display: flex; flex-direction: column;">
			<div style="font-size: 1rem; min-width: 125px; display: flex; align-items: center;">lastpass/<img id="rep3image" class="repimage" style="margin-left: 0.25rem width: 0px; height: 0px;" src="../images/chrome_lGoPS9sQw2.png" alt="testimage3"></div>
			<div id="rep3text" style="font-size: 0.75rem; margin-top: -0.35rem">opennam-auth-node</div>
		</div>
	</div>
</div>

<div class="authenticate_box" on:click={handleRoute}>
	<div class="authenticate_text">Continue!</div>
	<div class="purple_auth_bar"></div>
	<div class="blue_auth_bar"></div>
</div>


<style>

	.authenticate_box {
		display: flex;
		flex-direction: column;
		width: 100%;
		justify-content: center;
		align-items: center;
		margin-top: 2.2rem;
		font-size: 1.5rem;
	}

.purple_auth_bar {
		width: 45%;
		height: 5px;
		display: inline-block;
		background-color: #b193ff;
		border-radius: 50px;
		margin-top: 0.5rem;
	}

	.blue_auth_bar {
		width: 25%;
		height: 5px;
		display: inline-block;
		background-color: #6d93ff;
		border-radius: 50px;
		margin-top: 0.5rem;
	}

	.repimage {
		margin-left: 0.25rem;
	}

	.rep {
		display: flex;
		justify-content: center;
		margin-top: 0.75rem;
		opacity: 0;
		animation: show-grid  1.2s linear forwards;
		animation-iteration-count: 1
	}

	.rep1 {
		animation-delay: 1s;
	}
	.rep2 {
		animation-delay: 1.2s;
	}
	.rep3 {
		animation-delay: 1.4s;
	}


	.setup_title {
		font-size: 3em;
		text-align: center;
		margin-top: 1rem;
		margin-bottom: 0.5rem;
	}
	.white_bar {
		height: 4rem;
		width: 4px;
		background-color: white;
		display: inline-block;
		border-top-right-radius: 25px;;
		border-bottom-right-radius: 25px;
	}


	.lds-grid {
  display: inline-block;
  position: relative;
  width: 1.5rem;
  transform: scale(0.3);
  height: 80px;
}
.lds-grid div {
  position: absolute;
  width: 16px;
  height: 16px;
  border-radius: 50%;
  background: #fff;
  animation: lds-grid 1.2s linear infinite;
}
.lds-grid div:nth-child(1) {
  top: 8px;
  left: 8px;
  animation-delay: 0s;
}
.lds-grid div:nth-child(2) {
  top: 8px;
  left: 32px;
  animation-delay: -0.4s;
}
.lds-grid div:nth-child(3) {
  top: 8px;
  left: 56px;
  animation-delay: -0.8s;
}
.lds-grid div:nth-child(4) {
  top: 32px;
  left: 8px;
  animation-delay: -0.4s;
}
.lds-grid div:nth-child(5) {
  display: none;
}
.lds-grid div:nth-child(6) {
  top: 32px;
  left: 56px;
  animation-delay: -1.2s;
}
.lds-grid div:nth-child(7) {
  top: 56px;
  left: 8px;
  animation-delay: -0.8s;
}
.lds-grid div:nth-child(8) {
  top: 56px;
  left: 32px;
  animation-delay: -1.2s;
}
.lds-grid div:nth-child(9) {
  top: 56px;
  left: 56px;
  animation-delay: -1.6s;
}
@keyframes lds-grid {
  0%, 100% {
    opacity: 1;
  }
  50% {
    opacity: 0.5;
  }
}


@keyframes show-grid {
	0% {
		opacity: 0;
	}
	100% {
		opacity: 1;
	}
}


</style>
