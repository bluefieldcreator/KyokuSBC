<script>
	import ShopItem from '$lib/shop-item.svelte';
	import { slide } from 'svelte/transition';

	import { writable } from 'svelte/store';
	
	/**
	 * @type {any}
	 */
	let data = writable([]);
	let dropdownVisisble = false;
	let json = import('./data.json').then((JData) => {
		console.log(JData.default);
		data.set(JData.default);
	});
</script>

<div class="p-3 mt-10 sm:flex mx-auto w-9/12  items-center justify-between gap-1">
	<div class="font-bold text-3xl">Catalog</div>
	<div class="flex items-center font-bold gap-2">
		<div class="main p-2 rounded">Auctions</div>
		<input type="text" placeholder="Search..." class="p-2 main rounded" />
		<!-- This example requires Tailwind CSS v2.0+ -->
		<div class="relative inline-block text-left">
			<div>
				<button
					type="button"
					class="p-2 main rounded text-blue-600"
					id="menu-button"
					aria-expanded="true"
					aria-haspopup="true"
					on:click = {() => dropdownVisisble = !dropdownVisisble}
				>
					Filters
					<!-- Heroicon name: solid/chevron-down -->
					<li class="fa fa-chevron-down"></li>
				</button>
			</div>

			<!--
	  Dropdown menu, show/hide based on menu state.
  
	  Entering: "transition ease-out duration-100"
		From: "transform opacity-0 scale-95"
		To: "transform opacity-100 scale-100"
	  Leaving: "transition ease-in duration-75"
		From: "transform opacity-100 scale-100"
		To: "transform opacity-0 scale-95"
	-->
			{#if dropdownVisisble}
				<div transition:slide
					class="origin-top-right absolute right-0 mt-2 w-56 rounded-md shadow-lg bg-white ring-1 ring-black ring-opacity-5 focus:outline-none"
					role="menu"
					aria-orientation="vertical"
					aria-labelledby="menu-button"
					tabindex="-1"
				>
					<div class="py-1" role="none">
						<!-- Active: "bg-gray-100 text-gray-900", Not Active: "text-gray-700" -->
						<a
							href="#"
							class="text-gray-700 block px-4 py-2 text-sm"
							role="menuitem"
							tabindex="-1"
							id="menu-item-0">Account settings</a
						>
						<a
							href="#"
							class="text-gray-700 block px-4 py-2 text-sm"
							role="menuitem"
							tabindex="-1"
							id="menu-item-1">Support</a
						>
						<a
							href="#"
							class="text-gray-700 block px-4 py-2 text-sm"
							role="menuitem"
							tabindex="-1"
							id="menu-item-2">License</a
						>
						<form method="POST" action="#" role="none">
							<button
								type="submit"
								class="text-gray-700 block w-full text-left px-4 py-2 text-sm"
								role="menuitem"
								tabindex="-1"
								id="menu-item-3">Sign out</button
							>
						</form>
					</div>
				</div>
			{/if}
		</div>
	</div>
</div>
<div class="container mx-auto gap-2 flex">
	<div class="main p-4 rounded w-[40rem] flex items-center justify-center h-36">
		ITEM AD GOES HERE
	</div>
	<div class="main p-4 rounded flex-1 flex items-center justify-center h-36">
		ITEM AD GOES HERE

	</div>
</div>
<div class="container    mt-5 grid sm:grid-cols-2 md:grid-cols-3 xl:grid-cols-6 gap-5  mx-auto">
	{#each $data as item}
		<ShopItem title={item.AssetName} price={item.Price} rare={item.Limited} id={item.AssetID} />
	{/each}
</div>
