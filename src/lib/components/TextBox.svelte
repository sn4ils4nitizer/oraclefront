<script lang="ts">
	export let value: string;
</script>

<textarea bind:value rows="20" cols="40" class="textarea"></textarea>

<style>
	.textarea {
		resize: none;
		font-family: monospace;
		align-self: center;
		background-color: var(--honeydew);
		color: var(--raisin-black);
	}
</style>
