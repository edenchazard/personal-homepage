<script lang="ts">
	let { title, href } = $props();
</script>

<a target="_blank" class="flex h-26 w-36 flex-col items-center gap-2 p-4" {href}>
	<span class="inline-block size-8 border border-rose-400"></span>
	<span class="flex max-w-full flex-1 truncate text-xs text-wrap">{title}</span>
</a>
