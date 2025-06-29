<script lang="ts">
	import type { Snippet } from 'svelte';
	import { Portal } from '@jsrob/svelte-portal';
	import { base } from '$app/paths';

	let { icon, children, title, close } = $props<{
		children?: Snippet;
		title: string;
		close?: () => void;
		icon: Snippet;
	}>();

	let modalElement: HTMLDialogElement | undefined;
</script>

<Portal target="#desktop">
	<dialog
		open
		bind:this={modalElement}
		class="absolute top-0 bottom-0 size-full overflow-hidden md:m-auto md:max-h-[28rem] md:max-w-2xl md:rounded-md md:border md:bg-white md:shadow-lg"
	>
		<div
			class="flex h-full w-full flex-1 flex-col gap-0.5 rounded-sm border border-purple-950 bg-cyan-200 p-1 shadow-[3px_4px_3px_0px_#42006e]"
		>
			<header class="inset-shadow flex gap-4 font-bold text-indigo-700">
				<div
					class="flex w-full items-center gap-1 overflow-hidden rounded-sm border border-purple-950 bg-fuchsia-300 pl-1 text-xs *:py-1"
				>
					{@render icon()}
					<span class="flex-1">{title}</span>
					<a
						href={`${base}/desktop`}
						class="box-content size-4 border border-dotted text-center"
						onclick={() => close?.()}>x</a
					>
				</div>
			</header>
			<main
				class="flex flex-1 flex-col overflow-y-auto rounded-sm border border-purple-950 bg-purple-50 p-2"
			>
				{@render children?.()}
			</main>
			<footer class="flex items-center gap-2 px-2 text-xs font-bold text-indigo-700">
				<span class="inline-block size-2 animate-pulse rounded-full bg-red-500"> </span>
				REC
			</footer>
		</div>
	</dialog>
</Portal>
