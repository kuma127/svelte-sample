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
    <div id="plot"></div>
    <py-script>
import matplotlib.pyplot as plt
from data import make_x_and_y

x, y = make_x_and_y(n=1000)

fig, ax = plt.subplots()
ax.scatter(x, y)
pyscript.write('plot', fig)
    </py-script>
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