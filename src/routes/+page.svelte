<script>
	import ModalEdenetExplorer from '$lib/+ModalEdenetExplorer.svelte';
	import Taskbar from '$lib/+taskbar.svelte';
</script>

<div class="flex h-dvh w-dvw bg-black font-mono">
	<div class="flex size-full flex-1 flex-col items-center justify-center">
		<div class="relative flex h-full max-h-[50rem] w-full max-w-4xl flex-col bg-blue-100">
			<div class="flex flex-col px-2 text-center">
				<button type="button" class="h-26 w-20 text-xs">PinkedIn</button>
				<button type="button" class="h-32 w-20 text-xs">Garden of Eden</button>
				<button type="button" class="h-32 w-20 text-xs">Unicreatures Archive</button>
				<button type="button" class="h-32 w-20 text-xs">FART</button>
			</div>

			<div class="flex flex-1">
				<ModalEdenetExplorer />
			</div>

			<Taskbar />
		</div>
	</div>
</div>
