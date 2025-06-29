<script lang="ts">
	import '../app.css';
	import Taskbar from '$lib/Taskbar.svelte';
	import DesktopButton from '$lib/DesktopButton.svelte';
	import IconContext from 'phosphor-svelte/lib/IconContext';

	let { children } = $props();
</script>

<IconContext values={{ size: 30, mirrored: false, weight: 'light' }}>
	<div class="flex flex-1">
		<div class="flex size-full flex-1 flex-col items-center justify-center">
			<div class="relative flex w-full max-w-4xl flex-1 flex-col bg-blue-100">
				<div id="desktop" class="relative h-full w-full flex-1 overflow-hidden p-6">
					<!-- Dragcave group -->
					<div class="relative inline-flex rounded-md bg-white/40">
						<div class="absolute -top-2 right-0 left-0 text-center text-xs">
							<span class="rounded-sm bg-rose-100 px-2 py-1">Dragcave!</span>
						</div>
						<div class="flex flex-wrap gap-4">
							<DesktopButton title="Garden of Eden" href="https://chazza.me/dc/hatchery" />
							<DesktopButton title="FART" href="https://chazza.me/dc/auto-refresher" />
							<DesktopButton title="Lineage Builder" href="https://chazza.me/dc/lineage-builder" />
							<DesktopButton title="Calendar" href="https://chazza.me/dc/calendar" />
						</div>
					</div>

					<!-- Misc -->
					<DesktopButton
						title="Unicreatures Archive"
						href="https://chazza.me/unicreatures/creatures"
					/>
					<div class="absolute right-0 bottom-0 p-8">
						<DesktopButton title="Recycle Bin" href="https://chazza.me/dc/recycle-bin" />
						<div class="opacity-50">
							<p>Activate Winmoes</p>
							<p class="text-xs">Go to your settings</p>
						</div>
					</div>
				</div>
				<div class="flex">
					{@render children()}
				</div>
				<Taskbar />
			</div>
		</div>
	</div>
</IconContext>
