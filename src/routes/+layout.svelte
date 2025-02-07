<script lang="ts">
	import '../app.css';

	let { children } = $props();
</script>

<svelte:head>
	<title>Unikorn</title>
	<script src="/iconify-icon-1.0.5.min.js"></script>
</svelte:head>

{@render children()}
