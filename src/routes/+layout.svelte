<script lang="ts">
	import '../app.css';
	import Taskbar from '$lib/Taskbar.svelte';
	import DesktopButton from '$lib/DesktopButton.svelte';

	let { children } = $props();
</script>

<div class="flex h-dvh w-dvw bg-black font-mono">
	<div class="flex size-full flex-1 flex-col items-center justify-center">
		<div class="relative flex h-full max-h-[50rem] w-full max-w-4xl flex-col bg-blue-100">
			<div class="flex flex-col px-2 text-center">
				<DesktopButton title="Garden of Eden" href="https://chazza.me/dc/hatchery" />
				<DesktopButton title="FART" href="https://chazza.me/dc/auto-refresher" />
				<DesktopButton title="Lineage Builder" href="https://chazza.me/dc/lineage-builder" />
				<DesktopButton title="Calendar" href="https://chazza.me/dc/calendar" />
				<DesktopButton
					title="Unicreatures Archive"
					href="https://chazza.me/unicreatures/creatures"
				/>
			</div>
			<div class="flex flex-1">
				{@render children()}
			</div>
			<Taskbar />
		</div>
	</div>
</div>
