<script lang="ts">
	import Header from './Header.svelte';
	let name = $state('Donatas');

	let status: 'OPEN' | 'CLOSED' = $state('OPEN');

	let full_name = $derived(name + ' ' + 'Tubutis');

	function toggle() {
		// Mutate the variable itself!
		status = status === 'OPEN' ? 'CLOSED' : 'OPEN';
	}
</script>

<!-- can also write as <Header {name}> -->
<Header {name} fake_name={'brolis'} />

<h2>{full_name}</h2>
<input type="text" bind:value={name} />

<p>The store is now {status}</p>
<p></p>
<button onclick={toggle}>Toggle Status</button>

<!-- Could also do this shorthand if there is a named function onclick-->
<!-- <button {onclick}>Toggle.... -->

<!-- Can also do it inline! -->
<button
	onclick={() => {
		status = status === 'OPEN' ? 'CLOSED' : 'OPEN';
	}}>Toggle Status</button
>

<style>
</style>
