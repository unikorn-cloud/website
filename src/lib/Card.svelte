<script lang="ts">
	import type { Snippet } from 'svelte';

	interface Props {
		icon: string;
		title: string;
		content: Snippet;
		link: string;
	}

	let { icon, title, content, link }: Props = $props();
</script>

<article
	class="row-span-full flex flex-col gap-4 rounded-lg border border-[rgb(63,128,128)] p-2 shadow-[0_0_15px_2px_rgb(63,128,128)] lg:grid lg:grid-rows-subgrid lg:p-4"
>
	<div class="flex flex-col gap-4">
		<iconify-icon {icon} class="text-4xl"></iconify-icon>
		<h1 class="font-bold lg:text-xl">{title}</h1>
	</div>

	<div class="flex flex-col gap-4">
		{@render content()}
	</div>

	<a class="self-start justify-self-start rounded bg-[rgb(63,128,128)] p-4" href={link}>
		Learn More
	</a>
</article>
