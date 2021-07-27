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

	const onClickEventHandler = () => {
		expandLinks = !expandLinks;
	};

	onMount(() => {
		windowWidth = window.innerWidth;
	});
</script>

<svelte:window on:resize={onResizeHandler} />
<div
	on:click={onClickEventHandler}
	style="background-color: {bcgColor}; color: {color}"
	id="wrapper"
>
	<slot />
	<h3>{header}</h3>
	<p>{bodyText}</p>
	{#if links.length > 0}
		{#if windowWidth > 1024}
			<div class="linkWrapper">
				{#each links as link}
					<a style="border: 1px solid {color}" class="link" href={link.url}>{link.title}</a>
				{/each}
			</div>
		{:else}
			<div class="centerRight">
				<ExpandButton isOpen={expandLinks} />
			</div>
			{#if expandLinks}
				<div class="linkWrapper">
					{#each links as link}
						<a style="border-color: {color}" class="link" href={link.url}>{link.title}</a>
					{/each}
				</div>
			{/if}
		{/if}
	{/if}
</div>

<style lang="scss">
	.centerRight {
		position: absolute;
		right: 25px;
		top: 30px;
	}
	.linkWrapper {
		margin: 10px 0;

		@media (max-width: 767px) {
			margin: 0;
			padding: 0;
			display: block;
			width: 100%;
		}
	}
	.link {
		padding: 7px 10px;
		margin: 0px 5px;
		text-transform: uppercase;
		font-size: 12px;
		font-family: 'HM Sans Semi Bold', 'ヒラギノ角ゴ Pro W3', 'Hiragino Kaku Gothic Pro', Osaka,
			'メイリオ', Meiryo, 'ＭＳ Ｐゴシック', 'MS PGothic', sans-serif;
		border-style: solid;
		border-width: 1px;

		@media (max-width: 767px) {
			margin: 0;
			padding: 0;
			box-sizing: border-box;
			width: 100%;
			display: block;
			border-width: 0px;
			background-color: white;
			color: black;
			font-weight: 600;
			padding: 15px;
		}
	}
	.link:hover {
		background-color: rgb(238, 238, 238);
    color: rgb(247, 247, 247);
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
    hyphens: auto;
		font-weight: 600;
		font-size: 1.5em;
		margin-bottom: 0;
		margin-left: 70px;
		margin-right: 70px;
		text-align: center;
	}
	p {
		font-size: 0.6em;
		margin-top: 0;
		margin-left: 70px;
		margin-right: 70px;
		text-align: center;
	}
</style>
