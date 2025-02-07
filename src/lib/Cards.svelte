<script lang="ts">
	import type { Snippet } from 'svelte';

	interface Props {
		children?: Snippet;
	}

	let { children }: Props = $props();
</script>

<div class="flex flex-col gap-4 lg:grid lg:grid-cols-3 lg:grid-rows-[repeat(3,max-content)]">
	{@render children?.()}
</div>
