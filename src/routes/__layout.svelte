<script>
	import './../app.css';

</script>

<div class="items-center main justify-around text-white p-4 shadow sm:flex">
	<a href="/"><div class="text-center text-2xl font-extrabold antialiased">KyokuSBC</div></a>
	<div class="flex items-center justify-center gap-3 text-gray-400">
		<a href="/" class="hover:underline hover:text-white">Homepage</a>
		<a href="/shop" class="hover:underline hover:text-white	">Shop</a>
		<a href="/" class="hover:underline hover:text-white">Users</a>
		<a href="/" class="hover:underline hover:text-white">More</a>
	</div>
	<div class="flex items-center justify-center gap-3">
		<a href="/login"
			><div class=" border border-gray-500 rounded bg-[#2f2f2f] px-2 py-1 hover:text-white">Login</div></a
		>
		<a href="/register"
		><div class=" border border-gray-500 rounded bg-[#2f2f2f] px-2 py-1 hover:text-white">Register</div></a
		>
	</div>
</div>

<slot />
