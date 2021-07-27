<script lang="ts">
	import { page } from '$app/stores';
	import logo from '../../../static/HMLogo.svg';
</script>

<header>
	<div id="logo">
		<a href="/">
			<img width="80" src={logo} alt="SvelteKit" />
		</a>
	</div>

	<nav>
		<ul>
			<li class:active={$page.path === '/women'}><a sveltekit:prefetch href="/#">Women</a></li>
			<li class:active={$page.path === '/men'}><a sveltekit:prefetch href="/#">Men</a></li>
			<li class:active={$page.path === '/divided'}><a sveltekit:prefetch href="/#">Divided</a>
			</li>
			<li class:active={$page.path === '/about'}><a sveltekit:prefetch href="/about">About</a></li>
		</ul>
	</nav>
</header>

<style>
	#logo {
		padding-top: 40px;
	}
	header {
		width: 100%;
		display: flex;
		justify-content: center;
		align-items: center;
		flex-direction: column;
	}
	nav {
		padding-top: 20px;
		width: 300px;
	}
	ul {
		display: flex;
		justify-content: space-between;
		margin: 0;
		padding: 0;
	}
	li {
		list-style: none;
		display: inline-block;
	}
</style>
