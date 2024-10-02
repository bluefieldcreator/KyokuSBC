<script context="module">
	/** @type {import("./[id]").Load} */
	export const load = ({ params }) => {
		return {
			props: { id: params.id }
		};
	};
</script>

<script>
	export let id;
</script>

<div>
	<div class="container mx-auto mt-5 p-2">
		<div class="flex justify-center gap-5 mx-auto">
			<div class="border border-black p-2 h-[412px] w-[412px]">
				<img src="https://polytoria.com/assets/thumbnails/catalog/17224.png?v=1" alt="">
			</div>
			<div class="border text-right space-y-2 border-black p-2 w-2/4  h-fit" >
				<div class="text-6xl font-bold ">R&B Shades</div>
				<div class="text-green-500 font-bold text-3xl font-mono">30 <li class="fa fa-circle-dollar-to-slot"></li></div>
			</div>
		</div>
	</div>
</div>
