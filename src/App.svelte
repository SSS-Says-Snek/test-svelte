<script>
	let name = "";
	let notes = [
		{"value": "Watch the entire Breaking Bad TV Series"},
		{"value": "Watch the entire Better Call Saul TV Series"},
		{"value": "PPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPP"},
		{"value": "Consume dihydrogen monoxide"},
		{"value": "Sleep"},
		{"value": "I don't know anymore"},
		{"value": "I wholeheartedly agree with your opinion"}
	];

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

	<h2>Current Notes</h2>
	
	<div class="note-container">
	{#each notes as note}
		<div class="note">
			{note.value}
			<button>
				Delete
			</button>
		</div>
	{/each}
	</div>

</main>

<style>
	main {
		display: flex;
		flex-direction: column;
		align-items: center;
		padding: 1em;
	}

	h1, h2 {
		color: #ff3e00;
		text-transform: uppercase;
		font-weight: 100;
	}

	h1 {
		font-size: 4em;
	}

	h2 {
		font-size: 2em;
	}

	.note {
		border: 1px solid;
		border-radius: 5px;
		box-shadow: 0px 0px 3px black;
		padding: 1em 2em;

		min-width: 200px;
		width: max-content;
		max-width: 35vw;

		overflow-wrap: break-word;
	}

	.note-container {
		display: grid;
		grid-template-columns: 1fr;
		gap: 15px;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>