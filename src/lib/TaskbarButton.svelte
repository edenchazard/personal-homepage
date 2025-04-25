<script lang="ts">
	import { base } from '$app/paths';
	import { page } from '$app/state';
	let { href, title } = $props();
</script>

<a
	href={`${base}${href}`}
	type="button"
	class={[
		'taskbar-button box-content h-6 px-2',
		{
			selected: page.url.pathname === href
		}
	]}
>
	<span class="taskbar-button-icon"></span>
	<span>{title}</span>
</a>
