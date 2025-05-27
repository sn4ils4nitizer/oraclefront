<script lang="ts">
	import SubmitButton from "$lib/components/SubmitButton.svelte";
	import TextBox from "$lib/components/TextBox.svelte";
	import NavBar from "$lib/components/NavBar.svelte";
	import Button from "$lib/components/Button.svelte";

	let text = "";
	let audioplayer: HTMLAudioElement | null = null;

	async function handleSubmit() {
		const res = await fetch(
			"http://192.168.1.30/api/oracle/prompt",
			{
				method: "POST",
				mode: "cors",
				body: text,
			},
		);

		if (!res.ok) {
			console.error("Request failed 😭");
			return;
		}
		if (audioplayer) {
			audioplayer.pause();
			audioplayer.currentTime = 0;
		}
		text = "";
		const blob = await res.blob();
		audioplayer = new Audio(URL.createObjectURL(blob));
		audioplayer.play();
	}
</script>

<div class="center">
	<Button text="Test" width="80px" height="40px" />
	<TextBox bind:value={text} />
	<SubmitButton on:click={handleSubmit} />
</div>

<style>
	:global(body) {
		/* background-color: #212227; */
		background-color: black;
	}

	.center {
		text-align: center;
		display: flex;
		flex-flow: column;
		justify-content: center;
		height: 100vh;
	}
</style>
