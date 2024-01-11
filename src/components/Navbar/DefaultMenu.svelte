<script>
	import { onMount } from 'svelte';

	$: path = '';
	const routes = ['/', '/about', '/portfolio', '/contact'];

	onMount(() => (path = window.location.pathname));
</script>

<ul class="menu menu-horizontal px-1" class:hidden={!routes.includes(path)}>
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
