<script>
    let firstName = '';
	let lastName = '';
	$: fullName = `${firstName} ${lastName}`;

	let checked = false;

	const persons = [
		{name: 'Alice'},
		{name: 'Bob'},
		{name: 'Carol'}
	];
</script>

<div>
    <div>{fullName}</div>
    <input placeholder="Enter your name" bind:value={firstName}>
	<input placeholder="Enter your name" bind:value={lastName}>

	<label>
		<input type="checkbox" bind:checked={checked}>
		Check me!
	</label>

	{#if checked}
		<div>Checked!</div>
	{:else}
		<div>Non-Checked</div>
	{/if}

	{#each persons as p}
		<div>{p.name}</div>
	{/each}
</div>