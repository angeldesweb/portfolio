<script>
	import { onMount } from 'svelte';
	import { Menu } from '../icons';
	import BrandLink from './Navbar/BrandLink.svelte';
	import MobileMenu from './Navbar/MobileMenu.svelte';
	import DefaultMenu from './Navbar/DefaultMenu.svelte';

	let path;

	const routes = ['/', '/about', '/portfolio', '/contact'];

	onMount(() => {
		path = window.location.pathname;
	});
</script>

<div class="navbar glass mb-8">
	<div class="navbar-start">
		<div class="dropdown">
			<div
				tabindex="0"
				role="button"
				class="btn btn-ghost lg:hidden"
				class:hidden={!routes.includes(path)}
			>
				<Menu />
			</div>
			<MobileMenu />
		</div>
		<BrandLink />
	</div>
	<div class="navbar-center hidden lg:flex">
		<DefaultMenu />
	</div>
	<div class="navbar-end"></div>
</div>
