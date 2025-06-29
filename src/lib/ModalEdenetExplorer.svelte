<script lang="ts">
	import { onMount } from 'svelte';
	import Modal from './Modal.svelte';
	import WindowsLogo from 'phosphor-svelte/lib/WindowsLogo';

	const generator = commentPoolGenerator();
	let comments: string[] = $state([]);
	let commentsContainerElement: HTMLDivElement | undefined;
	let timeout: ReturnType<typeof setTimeout> | undefined;

	$effect(() => {
		comments;

		if (!commentsContainerElement) {
			return;
		}

		commentsContainerElement.scrollTo({
			top: commentsContainerElement.scrollHeight,
			behavior: 'smooth'
		});
	});

	onMount(beginCommentRotation);

	function handleVisibilityChange() {
		if (document.visibilityState === 'visible') {
			beginCommentRotation();
		} else {
			clearTimeout(timeout);
		}
	}

	function beginCommentRotation() {
		comments = [...comments, generator.next().value];
		timeout = setTimeout(beginCommentRotation, Math.floor(Math.random() * 2000) + 1000);
	}

	function* commentPoolGenerator(): Generator<string> {
		const commentDictionary = [
			'He really knows what a CSS is!',
			'weird name',
			'stop swearing guys',
			'lorem ipsum',
			'HELLO WORLD!!!!',
			'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec a diam lectus. Sed sit amet ipsum mauris.',
			'Maecenas congue ligula ac quam viverra nec consectetur ante hendrerit. Donec et mollis dolor.',
			'Praesent et diam eget libero egestas mattis sit amet vitae augue. Donec sodales sagittis magna.',
			'It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout.',
			'No one reads these'
		];

		const pool = [...commentDictionary];

		while (true) {
			const randomCommentIndex = Math.floor(Math.random() * pool.length);
			const comment = pool[randomCommentIndex];
			pool.splice(randomCommentIndex, 1);

			if (!pool.length) {
				// Reset when empty, but make sure that the next generated comment is not the same as the current one
				pool.push(...commentDictionary.filter((c) => c !== comment));
			}
			console.log('pick');
			yield comment;
		}
	}
</script>

<svelte:document onvisibilitychange={handleVisibilityChange} />

<Modal title="Edenet Explorer">
	{#snippet icon()}
		<WindowsLogo />
	{/snippet}
	<div class="flex items-center gap-2 rounded-sm bg-white p-1 text-red-500">
		&#11208; <span class="leading-3">Live</span>
		<div class="flex-1 self-stretch border border-rose-100 text-right">
			<span class="inline-block h-full w-12 bg-rose-100"></span>
		</div>
	</div>

	<div class="flex flex-1 pt-4 pr-8 pl-4">
		<div class="grid w-full grid-cols-[1.5fr_1fr] gap-4">
			<div class="h-40 w-full border border-rose-200"></div>

			<div
				class="order-3 col-span-full row-span-2 flex flex-col border border-rose-200 md:order-none md:col-span-1"
			>
				<p class="bg-white py-0.5 pl-4 text-center">
					<span class="inline-block w-full bg-purple-100 p-0.5 text-xs font-bold text-indigo-700">
						Comments...
					</span>
				</p>
				<div
					class="flex-1 overflow-hidden bg-purple-100 p-3 text-sm text-indigo-700"
					bind:this={commentsContainerElement}
				>
					<ul class="max-h-28 list-inside list-[square] space-y-2">
						{#each comments as comment}
							<li>{comment}</li>
						{/each}
					</ul>
				</div>
				<div class="bg-white px-2 py-1">
					<div class="grid grid-cols-[auto_1fr] items-center gap-x-2 gap-y-1">
						<span class="taskbar-button-icon col-start-1 row-span-2"> </span>
						<span class="col-start-2 row-start-1 h-1 w-8 bg-rose-200"></span>
						<span class="col-start-2 row-start-2 h-1 w-20 bg-gray-300"></span>
						<div
							class="col-span-full mt-1 flex items-center justify-between border-t border-rose-200 py-1"
						>
							<span class="taskbar-button-icon rounded-full bg-rose-200"> </span>
							<span class="text-rose-200"> &#11208; </span>
						</div>
					</div>
				</div>
			</div>

			<div class="order-2 col-span-full md:order-none md:col-span-1">
				<p class="text-lg font-bold text-purple-800">Hi, I'm Eden!</p>
				<ul class="mt-2 flex gap-2 text-sm">
					<li>100 likes</li>
					<li>Started streaming on DAY 1</li>
				</ul>
				<p class="mt-2 border-t border-purple-950 pt-2">I write code and make the magic happen.</p>
			</div>
		</div>
	</div>
</Modal>
