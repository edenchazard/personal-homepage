<script lang="ts">
	import Modal from '$lib/Modal.svelte';
</script>

<Modal title="P-please? uwu">
	<div class="flex h-full gap-8 p-4">
		<div class="flex w-48 items-center justify-items-center border border-rose-100 p-8">
			a cute anime girl here
		</div>
		<div class="flex flex-1 flex-col gap-4 text-center">
			<h1 class="text-left text-lg">H-hi there...</h1>
			<p>Do you th-think I could have your credit card information, p-please... ?</p>
			<form>
				<div class="grid grid-cols-2 gap-2">
					<label for="card-number">Card Number</label>
					<input
						class="bg-white p-2"
						type="text"
						id="card-number"
						placeholder="1234 5678 9012 3456"
					/>
					<label for="expiry-date">Expiry Date</label>
					<input class="bg-white p-2" type="text" id="expiry-date" placeholder="MM/YY" />
					<label for="cvv">CVV</label>
					<input class="bg-white p-2" type="text" id="cvv" placeholder="123" />
				</div>
				<button type="submit" class="mt-4 rounded bg-blue-500 p-2 text-white"> S-sure! </button>
				<button type="button" class="mt-4 rounded bg-red-500 p-2 text-white"> N-no way! </button>
			</form>
		</div>
	</div>
</Modal>
