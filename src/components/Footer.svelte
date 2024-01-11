<script>
	import { onMount } from 'svelte';

	$: path = '';

	onMount(() => (path = window.location.pathname));
</script>

<footer
	class="footer glass p-4 flex items-center justify-center"
	class:absol={!path || path === '/'}
>
	<span class="brand-text text-primary">angeldesweb - 2024</span>
</footer>
