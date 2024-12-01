<script lang="ts">
	// $props is a rune, new svelte 5 feature
	let {
		name,
		fake_name
	}: {
		name: string;
		fake_name?: string;
	} = $props();
</script>

<h1>Welcome to the shop {name}!</h1>

{fake_name}

<style>
</style>
