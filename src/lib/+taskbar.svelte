<script lang="ts">
	let interval: number;
	let time = '';

	$: {
		clearInterval(interval);
		interval = setInterval(() => {
			//if (browser) {
			time = new Date().toLocaleTimeString(undefined, {
				hour: '2-digit',
				minute: '2-digit',
				second: '2-digit'
			});
			//}
		}, 1000);
	}
</script>

<div class="flex items-center gap-2 border-t-2 border-purple-100 bg-purple-200 p-1 text-xs">
	<button type="button" class="start-button h-7 w-20 uppercase">Start</button>

	<div class="flex flex-1 items-center gap-2 text-indigo-700 *:box-content *:h-6 *:px-2">
		<button type="button" class="taskbar-button selected"
			><span class="taskbar-button-icon"></span><span> Edenet Explorer</span></button
		>
		<button type="button" class="taskbar-button"
			><span class="taskbar-button-icon"> </span><span>Flexplorer</span></button
		>
		<button type="button" class="taskbar-button"
			><span class="taskbar-button-icon"> </span><span> My Nomputer</span></button
		>
	</div>

	<div class="flex items-center text-purple-950">
		<span class="border-t border-l-2 border-purple-950 p-1">{time}</span>
	</div>
</div>
