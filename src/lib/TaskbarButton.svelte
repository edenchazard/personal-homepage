<script lang="ts">
	import { base } from '$app/paths';
	import { page } from '$app/state';

	let { href, title } = $props<{
		href: string;
		title?: string;
	}>();
</script>

<a
	href={`${base}${href}`}
	class={[
		'taskbar-button box-content h-6 px-2',
		{
			selected: page.url.pathname === href,
			'!border-none': !title
		}
	]}
>
	<span class="taskbar-button-icon"></span>
	{#if title}
		<span>{title}</span>
	{/if}
</a>
