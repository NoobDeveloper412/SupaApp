<script>
	import { goto } from '$app/navigation';
</script>

<nav class="bg-blue-500 p-4">
	<div class="container mx-auto flex justify-between items-center">
		<a href="/" class="text-white text-lg font-bold" on:click|preventDefault={() => goto('/')}
			>SupApp</a
		>
		<div>
			<a href="/about" class="text-white mx-2" on:click|preventDefault={() => goto('/signin')}
				>Sign-in</a
			>
			<a href="/contact" class="text-white mx-2" on:click|preventDefault={() => goto('/signup')}
				>Sign-up</a
			>
		</div>
	</div>
</nav>
