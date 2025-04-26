<script lang="ts">
	import type { Snippet } from 'svelte';
	import { Portal } from '@jsrob/svelte-portal';

	let { children, title, close } = $props<{
		children?: Snippet;
		title: string;
		close?: () => void;
	}>();

	let modalElement: HTMLDialogElement | undefined;

	function closeModal() {
		modalElement?.close?.();
		close?.();
	}
</script>

<Portal target="#desktop">
	<dialog
		open
		bind:this={modalElement}
		class="absolute inset-8 max-h-[28rem] w-full max-w-2xl md:inset-20"
	>
		<div
			class="flex w-full flex-1 flex-col gap-0.5 rounded-sm border border-purple-950 bg-cyan-200 p-1 shadow-[3px_4px_3px_0px_#42006e]"
		>
			<div class="inset-shadow flex gap-4 bg-fuchsia-300 font-bold text-indigo-700">
				<div
					class="flex w-full items-center gap-1 overflow-hidden rounded-sm border border-purple-950 pl-1 text-xs *:py-1"
				>
					<span class="taskbar-button-icon"> </span>
					<span class="flex-1">{title}</span>
					<button
						type="button"
						class="box-content size-4 border border-dotted text-center"
						onclick={() => closeModal()}>x</button
					>
				</div>
			</div>

			<div
				class="flex flex-1 flex-col overflow-y-auto rounded-sm border border-purple-950 bg-purple-50 p-2"
			>
				{@render children?.()}
			</div>
			<div class="flex items-center gap-2 px-2 text-xs font-bold text-indigo-700">
				<span class="inline-block size-2 animate-pulse rounded-full bg-red-500"> </span>
				REC
			</div>
		</div>
	</dialog>
</Portal>
