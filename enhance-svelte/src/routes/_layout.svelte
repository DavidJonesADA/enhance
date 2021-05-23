<script>
	import Nav from '../components/Nav.svelte';
</script>

<style>

@font-face {
    font-family: Ubuntu;
    src: url('../fonts/Ubuntu-Light.woff') format('woff');
    font-weight: 300;
    font-style: normal;
}

@font-face {
    font-family: Ubuntu;
    src: url('../fonts/Ubuntu.woff') format('woff');
    font-weight: normal;
    font-style: normal;
}
    :global(body){
        background-color: white;
        background-image: url("../images/background.png");
		width: 100vw;
		height: 100vh;
		background-repeat:no-repeat;
		background-size:cover;
		font-family: Ubuntu;
		
    }
</style>

<main>
	<slot></slot>
</main>