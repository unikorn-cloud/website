<script lang="ts">
	import type { Snippet } from 'svelte';
	import { assets } from '$app/paths';

	interface Props {
		title: string;
		headline?: Snippet;
		image?: string;
		image_alt?: string;
		image_class?: string;
		image_position?: string;
		children?: Snippet;
	}

	let {
		title,
		headline,
		image,
		image_alt,
		image_class,
		image_position = 'end',
		children
	}: Props = $props();
</script>

<section class="flex flex-col items-center gap-8 px-4 py-8 lg:flex-row lg:px-64 lg:py-16 lg:py-16">
	{#if image && image_position == 'start'}
		<img src={assets + image} alt={image_alt} class={image_class} />
	{/if}

	<div class="flex grow flex-col gap-8">
		<h1 class="text-2xl font-bold lg:text-3xl">{title}</h1>

		{#if headline}
			<p class="text-2xl">
				{@render headline()}
			</p>
		{/if}

		{@render children?.()}
	</div>

	{#if image && image_position == 'end'}
		<img src={assets + image} alt={image_alt} class={image_class} />
	{/if}
</section>
