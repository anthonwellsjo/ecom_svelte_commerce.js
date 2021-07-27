<script lang="ts">
	export let isOpen: boolean;
	// export let onClick: () => void;
	export let color = 'white';
</script>

<button>
	<div id="wrapper">
		<div id="horizontal" style="background-color: {color}" />
		{#if !isOpen}
			<div style="background-color: {color}" id="vertical" />
		{/if}
	</div>
</button>

<style>
  #wrapper{
    position: relative;
    display: flex;
    align-items: center;
    justify-content: center;
  }
	button {
		background: none;
		color: inherit;
		border: none;
		padding: 0;
		font: inherit;
		outline: inherit;
    width:20px;
    height :20px;
	}
	#horizontal {
    position: absolute;
		height: 1px;
		width: 15px;
	}
	#vertical {
    position: absolute;
		height: 15px;
		width: 1px;
	}
</style>
