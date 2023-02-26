<script context="module">
	import '../../app.css';
	import { onMount } from 'svelte';

	const players = new Set();
</script>

<script>
	export let src;

	let player;

	onMount(() => {
		// Like players.push(player)
		players.add(player);
	});
</script>

<div class="flex mx-2">
	<audio style="margin: 0 auto;" bind:this={player} {src} controls>
		<track kind="captions" />
	</audio>
</div>
