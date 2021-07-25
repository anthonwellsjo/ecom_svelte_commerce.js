<script context="module" lang="ts">
	export const prerender = true;
</script>

<script lang="ts">
	import Counter from '$lib/Counter.svelte';
</script>

<svelte:head>
	<title>Home</title>
</svelte:head>

<section>
	<p id="delivery">Free standard delivery and Click & Collect for Members</p>
</section>

<style>
  #delivery{
    font-size: .75em;
  }
	section {
    padding-top: 30px;
		display: flex;
		flex-direction: column;
		align-items: center;
		flex: 1;
	}
</style>
