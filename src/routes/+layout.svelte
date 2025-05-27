<script lang="ts">
	import TopBar from "$lib/components/TitleBar.svelte";
	import NavBar from "$lib/components/NavBar.svelte";
	// for later
</script>

<TopBar />
<NavBar />
<slot />

<!-- Pages come here -->

<style global>
	@import "../lib/styles/color.css";
</style>
