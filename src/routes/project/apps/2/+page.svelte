<main>
	<h1>Учет расходов</h1>
	<form>
		<label for="name">Название</label>
		<input bind:value={Name} id="name">
		<label for="count">Сумма</label>
		<input bind:value={Amount} id="count">
		<button on:click={() => addExpans()}><span>Добавить</span></button>
	</form>
	<table>
		<thead>
			<tr>
				<th>Название</th>
				<th>Сумма</th>
				<th>Действия</th>
			</tr>
		</thead>
		<tbody>
			{#each expanses as expanse, i }	
				<tr>
				<td><div>{expanse.name}</div></td>
				<td><div>{expanse.amount}</div></td>
				<td><button on:click={() => deleteExpense(i)}>Удалить</button></td>
			</tr>
			{/each}
		</tbody>
	</table>
</main>

<script>
	let expanses = [];
	let Name = '';
	let Amount = '';

	function addExpans() {
		const obj = {
			name: Name,
			amount: parseInt(Amount),
		};
		expanses.push(obj);
		expanses = expanses;
		Name = '';
		Amount = '';
	}
	function deleteExpense(index) {
		expanses.splice(index, 1);
		expanses = expanses;
	}
</script>
<style>
	label {
		display: block;
		margin-bottom: 10px;
	}
	
	input {
		padding: 5px;
		border: 1px solid #ddd;
		border-radius: 5px;
		margin-right: 5px;
		width: 150px;
	}
	table {
		margin-top: 20px;
		border-collapse: collapse;
		width: 100%;
	}

	th,td {
		border: 1px solid #ddd;
		padding: 8px;
		text-align: left;
	}

	th {
		background-color: #ddd;
	}

	button {
		padding: 5px 10px;
		background-color: #4caf50;
		color: white;
		border: none;
		border-radius: 5px;
		cursor: pointer;
	}
	h1 {
		font-size: 25px;
		margin-bottom: 20px;
	}
</style>
