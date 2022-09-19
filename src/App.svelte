<script>
	let name = "";
	let notes = [
		{editing: false, value: "Watch the entire Breaking Bad TV Series" },
		{editing: false, value: "Watch the entire Better Call Saul TV Series" },
		{editing: false, value: "PPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPP" },
		{editing: false, value: "Consume dihydrogen monoxide" },
		{editing: false, value: "Sleep" },
		{editing: false, value: "I don't know anymore" },
		{	editing: false, 
			value: "I wholeheartedly agree with your opinion, but because of the law of thermodynamics, I refuse to accept.",
		},
	];
</script>

<main>
	<h1>Hello{name ? " " : ""}{name}!</h1>

	<label>
		Name:
		<input
			type="text"
			bind:value={name}
			placeholder="Enter name"
			maxlength="16"
		/>
	</label>

	<label>
		Note:
		<input type="text" placeholder="Enter short note" maxlength="30" />

		<button>Send</button>
	</label>

	<h2>Current Notes</h2>

	<div class="note-container">
		{#each notes as note}
			<div class="note">
				{#if !note.editing}
					{note.value}
				{:else}
					<input value={note.value}>
				{/if}

				<div class="note-buttons">
					<button>Edit</button>
					<button>Delete</button>
				</div>
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
		display: flex;
		flex-direction: column;
		gap: 0.5em;

		border: 1px solid;
		border-radius: 5px;
		box-shadow: 0px 0px 3px black;
		padding: 1em 2em;

		min-width: 200px;
		max-width: 300px;

		word-break: break-all;
		align-items: center;
	}

	.note input {
		display: flex;
		flex: 1;
	}

	.note-container {
		display: grid;
		grid-template-columns: 1fr 1fr;
		gap: 15px;

		justify-content: center;

		/*border: 1px solid;*/
	}

	.note-buttons {
		display: flex;
		gap: 35px;
	}

	.note-buttons button {
		width: max-content;
		border: 1px solid rgba(34, 34, 34, 0.345);
		border-radius: 1em;
		box-shadow: 0px 0px 2px black;
		font-weight: light;
		transition: 300ms ease;
	}

	.note-buttons button:hover {
		transform: scale(1.1);
		background-color: rgba(169, 169, 169, 0.702);
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>
