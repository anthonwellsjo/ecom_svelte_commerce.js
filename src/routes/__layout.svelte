<script lang="ts">
	import Header from '$lib/header/Header.svelte';
	import '../app.scss';
</script>

<Header />

<main>
	<div id="frame">
		<slot />
	</div>
</main>

<footer />

<style>
  #frame{
    width:99%;
		max-width: 1024px;
  }
	main {
		flex: 1;
    width: 100%;
		display: flex;
		flex-direction: column;
		padding: 1rem;
		align-items: center;
		margin: 0 auto;
		box-sizing: border-box;
	}

	footer {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		padding: 40px;
	}

	@media (min-width: 480px) {
		footer {
			padding: 40px 0;
		}
	}
</style>
