<script>
	import PrimaryButton from './primary-button.svelte';
	import SecondaryButton from './secondary-button.svelte';

	export /**
	 * @type {string}
	 */
	let title;
	export /**
	 * @type {number}
	 */
	let price;
	export /**
	 * @type {boolean}
	 */
	let rare;

	/**
	 * @type {number}
	 */
	export let id;
</script>

<a href="/shop/item/{id}" class="">
	<div
		class=" overlay group h-[300px] main rounded transition-all duration-300  relative w-full {rare === true ? "border-yellow-500" : "border-[#242424]" } border-4   shadow-xl "
	>
		<img
			src="https://polytoria.com/assets/thumbnails/catalog/15075.png?v=1"
			class="object-cover  border-b border-gray-600 w-full h-2/4"
			alt=""
		/>
		<div class="p-2">
			<div class="text-3xl font-bold group-hover:underline truncate">{title}</div>
			<div class="">By <span class="link">Owner</span></div>
		</div>
		<div class="text-center  absolute p-1 -gap-6  bottom-0 w-full ">
			<PrimaryButton>Buy</PrimaryButton>
		</div>
	</div>
</a>
