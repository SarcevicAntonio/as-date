<script>
	import Popover from './Popover.svelte';

	/** Reactive outside value */
	export let value;

	/**
	 * Formats:
	 * JJJJ-MM-DD
	 * JS Date
	 */

	let open = false;
</script>

{value}

<span class="container">
	<input type="text" placeholder="JJJJ-MM-DD" />
	<button
		on:click={() => {
			open = !open;
		}}
	>
		open
	</button>
	{#if open}
		<Popover />
	{/if}
</span>

<style>
	.container {
		position: relative;
	}
</style>
