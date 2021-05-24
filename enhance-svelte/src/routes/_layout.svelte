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
		font-family: Ubuntu;
		
    }
</style>

<main>
	<slot></slot>
</main>