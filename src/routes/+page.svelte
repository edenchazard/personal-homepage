<script>
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
				<div
					class="absolute top-20 left-32 flex size-full max-h-[28rem] max-w-2xl flex-1 flex-col gap-0.5 rounded-sm border border-purple-950 bg-cyan-200 p-1 shadow-[3px_4px_3px_0px_#42006e]"
				>
					<div class="inset-shadow flex gap-4 bg-fuchsia-300 font-bold text-indigo-700">
						<div
							class="flex w-full items-center gap-1 overflow-hidden rounded-sm border border-purple-950 pl-1 text-xs *:py-1"
						>
							<span class="taskbar-button-icon"> </span>
							<span class="flex-1">Edenet Explorer</span>
							<button type="button" class="box-content size-4 border border-dotted text-center"
								>x</button
							>
						</div>
					</div>

					<div
						class="flex flex-1 flex-col overflow-y-auto rounded-sm border border-purple-950 bg-purple-50 p-2"
					>
						<div class="flex items-center gap-2 rounded-sm bg-white p-1 text-red-500">
							&#11208; <span class="leading-3">Live</span>
							<div class="flex-1 self-stretch border border-rose-100 text-right">
								<span class="inline-block h-full w-12 bg-rose-100"></span>
							</div>
						</div>

						<div class="flex flex-1 pt-4 pr-8 pl-4">
							<div class="grid w-full grid-cols-[1.5fr_1fr] gap-4">
								<div class="h-40 w-full border border-rose-200"></div>
								<div class="row-span-2 flex flex-col border border-rose-200">
									<p class="bg-white py-0.5 pl-4 text-center">
										<span
											class="inline-block w-full bg-purple-100 p-0.5 text-xs font-bold text-indigo-700"
											>Comments...</span
										>
									</p>
									<ul
										class="flex-1 list-inside list-[square] space-y-2 bg-purple-100 px-3 text-sm text-indigo-700"
									>
										<li>He really knows what a CSS is!</li>
										<li>weird name</li>
										<li>stop swearing guys</li>
									</ul>
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
								<div>
									<p class="text-lg font-bold text-purple-800">Hi, I'm Eden!</p>
									<ul class="mt-2 flex gap-2 text-sm">
										<li>100 likes</li>
										<li>Started streaming on DAY 1</li>
									</ul>
									<p class="mt-2 border-t border-purple-950 pt-2">
										I write code and make the magic happen.
									</p>
								</div>
							</div>
						</div>
					</div>
					<div class="flex items-center gap-2 px-2 text-xs font-bold text-indigo-700">
						<span class="inline-block size-2 animate-pulse rounded-full bg-red-500"> </span>
						REC
					</div>
				</div>
			</div>

			<Taskbar />
		</div>
	</div>
</div>
