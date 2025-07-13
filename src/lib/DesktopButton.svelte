<script lang="ts">
	let { title, href, src } = $props<{
		title: string;
		href: string;
		src?: string;
	}>();
</script>

<a target="_blank" class="flex h-26 w-36 flex-col items-center gap-2 p-4" {href}>
	<img class="inline-block size-12 border border-rose-400 object-contain" {src} alt="" />
	<span class="flex max-w-full flex-1 truncate text-center text-xs text-wrap">{title}</span>
</a>
