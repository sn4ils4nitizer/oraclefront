<script>
	export let text = "Button";
	export let height = "40px";
	export let width = "80px";
	export let onClick = () => {};
	export let className = "";
</script>

<button
	class={"button" + className}
	on:click={onClick}
	style="width: {width}; height: {height}; align-self: center;"
	>{text}</button
>

<style>
	.button {
		background-color: var(--salmon-pink);
		color: var(--raisin-black);
		border: 2px solid var(--raisin-black);
		padding: 0.5rem 1rem;
		border-radius: 16px;
		font-weight: bold;
		cursor: pointer;
		transition: all 0.2s ease-in-out;
		white-space: nowrap;
	}

	.button:hover {
		background-color: var(--light-coral);
		transform: scale(1.05);
	}
</style>
