<script lang="ts">
	import ExpandButton from '$lib/expandButton/expandButton.svelte';
	import { onMount } from 'svelte';

	export let bcgColor = 'red';
	export let color = 'black';
	export let header = 'Header';
	export let bodyText = 'BodyText';
	export let links: Array<{ title: string; url: string }> = [];

	let windowWidth: number;
	let expandLinks = false;

	const onResizeHandler = (e) => {
		windowWidth = e.currentTarget.innerWidth;
	};

	onMount(() => {
		windowWidth = window.innerWidth;
	});
</script>

<svelte:window on:resize={onResizeHandler} />
<div style="background-color: {bcgColor}; color: {color}" id="wrapper">
	<slot />
	<h3>{header}</h3>
	<p>{bodyText}</p>
	{#if links.length > 0}
		{#if windowWidth > 1024}
			<div class="bannerWrapper">
				{#each links as link}
					<a style="border: 1px solid {color}" class="link" href={link.url}>{link.title}</a>
				{/each}
			</div>
		{:else}
			<div class="centerRight">
				<ExpandButton
					isOpen={expandLinks}
					onClick={() => {
						expandLinks = !expandLinks;
					}}
				/>
			</div>
		{/if}
	{/if}
</div>

<style>
  .centerRight{
    position: absolute;
    right: 25px;
    top:25%;
  }
	.bannerWrapper {
		margin: 10px 0;
	}
	.link {
		padding: 7px 10px;
		margin: 0px 5px;
		text-transform: uppercase;
		font-size: 12px;
		font-family: 'HM Sans Semi Bold', 'ヒラギノ角ゴ Pro W3', 'Hiragino Kaku Gothic Pro', Osaka,
			'メイリオ', Meiryo, 'ＭＳ Ｐゴシック', 'MS PGothic', sans-serif;
	}

	#wrapper {
		width: 100%;
		position: relative;
		font-family: 'HM Sans Semi Bold', 'ヒラギノ角ゴ Pro W3', 'Hiragino Kaku Gothic Pro', Osaka,
			'メイリオ', Meiryo, 'ＭＳ Ｐゴシック', 'MS PGothic', sans-serif;
		display: flex;
		flex-direction: column;
		align-items: center;
		padding-top: -5px;
		padding-bottom: 15px;
	}
	h3 {
		font-weight: 600;
		font-size: 1.5em;
		margin-bottom: 0;
	}
	p {
		font-size: 0.6em;
		margin-top: 0;
	}
</style>
