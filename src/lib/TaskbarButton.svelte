<script lang="ts">
	import { base } from '$app/paths';
	import { page } from '$app/state';
	import type { Snippet } from 'svelte';

	let { href, title, icon } = $props<{
		href: string;
		title?: string;
		icon?: Snippet;
	}>();
</script>

<a
	href={`${base}${href}`}
	class={[
		'box-content flex h-6 items-center gap-2 border-t border-l-2 px-2 font-bold',
		{
			'bg-gray-300/70': page.url.pathname === href,
			'!border-none': !title
		}
	]}
>
	{@render icon?.()}
	{#if title}
		<span>{title}</span>
	{/if}
</a>
