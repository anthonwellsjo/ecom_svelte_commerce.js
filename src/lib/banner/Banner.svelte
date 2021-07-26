<script lang="ts">
	export let bcgColor = 'red';
	export let color = 'black';
	export let header = 'Header';
	export let bodyText = 'BodyText';
</script>

<div style="background-color: {bcgColor}; color: {color}" id="wrapper">
	<slot />
	<h3>{header}</h3>
	<p>{bodyText}</p>
</div>

<style>
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
