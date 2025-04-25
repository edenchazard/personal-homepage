<script lang="ts">
	import { onMount } from 'svelte';
	import TaskbarButton from './TaskbarButton.svelte';

	let interval = $state(0);
	let time = $state('00:00:00');

	onMount(() => {
		clearInterval(interval);
		interval = setInterval(() => {
			time = new Date().toLocaleTimeString(undefined, {
				hour: '2-digit',
				minute: '2-digit',
				second: '2-digit'
			});
		}, 1000);
	});
</script>

<div class="flex items-center gap-2 border-t-2 border-purple-100 bg-purple-200 p-1 text-xs">
	<button type="button" class="start-button h-7 w-20 uppercase">Start</button>

	<div class="flex flex-1 items-center gap-2 text-indigo-700">
		<TaskbarButton href="/" title="Edenet Explorer" />
		<TaskbarButton href="/portfolio" title="Flexplorer" />
		<TaskbarButton href="/" title="My Nomputer" />
	</div>

	<div class="flex items-center text-purple-950">
		<span class="border-t border-l-2 border-purple-950 p-1">{time}</span>
	</div>
</div>
