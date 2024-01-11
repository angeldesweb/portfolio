<script>
	import { onMount } from 'svelte';

	$: path = '';

	const routes = ['/', '/about', '/portfolio'];

	onMount(() => (path = window.location.pathname));
</script>

<ul
	tabindex="-1"
	class="menu menu-sm dropdown-content mt-3 p-2 shadow bg-base-100 rounded-box w-52"
	class:hidden={!routes.includes(path)}
>
	<li>
		<a href="/about" class:text-primary={path === '/about'}>Sobre mi</a>
	</li>
	<li>
		<a href="/portfolio" class:text-primary={path === '/portfolio'}>
			Portafolio
		</a>
	</li>
	<li>
		<a href="/contact" class:text-primary={path === '/contact'}>Contacto</a>
	</li>
</ul>

<style>
	.menu {
		z-index: 10;
	}
</style>
