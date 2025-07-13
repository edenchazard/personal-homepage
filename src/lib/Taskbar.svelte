<script lang="ts">
	import { onMount } from 'svelte';
	import TaskbarButton from './TaskbarButton.svelte';
	import Money from 'phosphor-svelte/lib/Money';

	let interval = $state<ReturnType<typeof setInterval>>();
	let time = $state('00:00:00');

	onMount(() => {
		tickTime();
		interval = setInterval(tickTime, 1000);
	});

	function tickTime() {
		time = new Date().toLocaleTimeString(undefined, {
			hour: '2-digit',
			minute: '2-digit'
		});
	}
</script>

<div
	class="flex gap-2 border-t-2 border-purple-100 bg-purple-200 p-1 text-xs md:flex-row md:items-center"
>
	<button
		type="button"
		class="start-button h-7 cursor-pointer border-r-2 border-b px-4 uppercase md:w-20"
	>
		Start
	</button>

	<div
		class="flex flex-1 divide-x-2 divide-black text-indigo-700 *:flex *:gap-[inherit] md:flex-row md:items-center md:*:px-4"
	>
		<div class="flex md:flex-row">
			<TaskbarButton href="/totally-not-a-scam" />
		</div>

		<div class="flex md:flex-row">
			<TaskbarButton href="/" title="Edenet Explorer" />
			<TaskbarButton href="/portfolio" title="Flexplorer" />
		</div>
	</div>

	<div class="hidden items-center text-purple-950 md:flex">
		<span class="border-t border-l-2 border-purple-950 p-1">{time}</span>
	</div>
</div>
