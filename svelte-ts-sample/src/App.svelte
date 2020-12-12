<script>
	import Card from './Card.svelte';
	import Jumble from './Jumble.svelte';
	import Message from './Message.svelte';
	import Home from './Home.svelte';

	const text = ['Hello!', 'Svelte!'];
	let current = 0;

	const toggle = () => current = (current + 1) % 2;
</script>

<main>
	<Card>
		{text[current]}
		<button on:click={toggle}>Toggle Message</button>
		<br>
		<Message message="This is test message."/>
	</Card>
	<Jumble></Jumble>

	<Home></Home>
</main>

<style>
	main {
		background-color: rgb(255, 251, 246);
		padding: 2em;
		width: 100%;
		height: 100%;
		overflow-y: auto;
	}
</style>