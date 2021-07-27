<script context="module" lang="ts">
	export const prerender = true;
</script>

<script lang="ts">
	import Banner from '$lib/banner/Banner.svelte';
</script>

<svelte:head>
	<title>Home</title>
</svelte:head>

<section>
	<p id="delivery">Free standard delivery and Click & Collect for Members</p>
	<Banner
		bcgColor="#c9002e"
		color="white"
		header="Added styles! Up to 50% off"
		bodyText="Valid on selected items in-store and at hm.com while stocks last. Stock may vary."
		links={[
      { title: 'Women', url: 'www.gp.se' },
      { title: 'Men', url: 'www.gp.se' },
      { title: 'Divided', url: 'www.gp.se' },
      ]}
	/>
</section>

<style>
	#delivery {
		font-size: 0.7em;
    text-align: center;
	}
	section {
		padding-top: 30px;
		display: flex;
		flex-direction: column;
		align-items: center;
		flex: 1;
	}
</style>
