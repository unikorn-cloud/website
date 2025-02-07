<script lang="ts">
	import type { Snippet } from 'svelte';

	interface Props {
		title: string;
		headline?: Snippet;
		children?: Snippet;
	}

	let { title, headline, children }: Props = $props();
</script>

<section id="what" class="flex flex-col gap-8 px-4 py-8 lg:px-64 lg:py-16 lg:py-16">
	<h1 class="text-2xl font-bold lg:text-3xl">{title}</h1>

	{#if headline}
		<p class="text-2xl">
			{@render headline()}
		</p>
	{/if}

	{@render children?.()}
</section>
