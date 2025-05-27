<script lang="ts">
	import { createEventDispatcher } from "svelte";

	const dispatch = createEventDispatcher();

	function handleClick() {
		dispatch("click");
	}
</script>

<button class="button" on:click={handleClick}>SUBMIT</button>

<style>
	.button {
		height: 40px;
		width: 298px;
		color: var(--raisin-black);
		background-color: var(--salmon-pink);
		align-self: center;
	}
</style>
