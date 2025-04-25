<script lang="ts">
	let { children, title } = $props();
</script>

<div
	class="absolute top-20 left-32 flex size-full max-h-[28rem] max-w-2xl flex-1 flex-col gap-0.5 rounded-sm border border-purple-950 bg-cyan-200 p-1 shadow-[3px_4px_3px_0px_#42006e]"
>
	<div class="inset-shadow flex gap-4 bg-fuchsia-300 font-bold text-indigo-700">
		<div
			class="flex w-full items-center gap-1 overflow-hidden rounded-sm border border-purple-950 pl-1 text-xs *:py-1"
		>
			<span class="taskbar-button-icon"> </span>
			<span class="flex-1">{title}</span>
			<button type="button" class="box-content size-4 border border-dotted text-center">x</button>
		</div>
	</div>

	<div
		class="flex flex-1 flex-col overflow-y-auto rounded-sm border border-purple-950 bg-purple-50 p-2"
	>
		{@render children()}
	</div>
	<div class="flex items-center gap-2 px-2 text-xs font-bold text-indigo-700">
		<span class="inline-block size-2 animate-pulse rounded-full bg-red-500"> </span>
		REC
	</div>
</div>
