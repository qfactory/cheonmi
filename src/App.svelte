<script>
import Home from './pages/Home.svelte';
import About from './pages/About.svelte';
import "smelte/src/tailwind.css" ;

let path = 'home'
// const src = './assets/pattern.png'
// $: bgImage = `background-image: url("${src}");`;
</script>
	<div class="wrap">
		<div class="background"  >
			<img src="./assets/pattern.png" alt="background" />
		</div>
		{#if path === 'home'}
			<Home bind:path></Home>
		{:else }
			<About bind:path></About>
		{/if}
	</div>

<style>

	.background{
		z-index: 0;
		position: fixed;
		width: inherit;
		max-height: inherit;
		top:0;
		opacity: 0.23;
		overflow: hidden;
		pointer-events: none;
	}
	.background>img{
		width: 100%;
		filter: blur(1px);
		/* object-fit: cover; */
	}
	
</style>