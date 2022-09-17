<script>
	let name = "";

</script>

<main>
	<h1>Hello{name ? ' ' : ''}{name}!</h1>

	<label>
		Name: 
		<input type="text" bind:value={name} placeholder="Enter name" maxlength=16>
	</label>

	<label>
		Note:
		<input type="text" placeholder="Enter short note" maxlength=30>

		<button>Send</button>
	</label>

	<h2>EEEE</h2>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	h2 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 2em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>