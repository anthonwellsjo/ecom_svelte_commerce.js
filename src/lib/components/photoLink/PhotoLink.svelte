<script lang="ts">
	let linkUrl: string;
	let element: HTMLDivElement;
	export let header: string = 'Header';
	export let bodyText: string = 'Body text';
  
</script>

<a  href={"#"}>
	<div class="inWrap" bind:this={element}>
		{#if element}
			<img width="100%" src="https://picsum.photos/2000" alt="yep" />
		{/if}
		<div class="overLay" />
		<div class="bodyDiv">
			<h3>{header}</h3>
			<p>{bodyText}</p>
		</div>
	</div>
</a>

<style lang="scss">
  a{
    cursor: pointer;
  }
	img {
		z-index: 0;
	}
	.overLay {
		position: absolute;
		top: 0;
    left:0;
    right:0;
    bottom:5px;
		background: linear-gradient(0deg, #00000099 5%, #ffffff84 100%);
		
	}
	.inWrap {
		position: relative;
		width: 100%;
    
	}
  .bodyDiv{
    position: absolute;
    bottom:10px;
    color: white;
    width: 100%;
    font-family: "HM Sans Bold","ヒラギノ角ゴ Pro W3","Hiragino Kaku Gothic Pro",Osaka,"メイリオ",Meiryo,"ＭＳ Ｐゴシック","MS PGothic",sans-serif;;

    h3{
      font-size: 1em;
      text-align: center;
      margin-bottom: -10px;
    }
    p{
      font-size: .8em;
      text-align: center;
    }
  }
</style>
