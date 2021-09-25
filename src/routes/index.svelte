<script>
	import Datepicker from '$lib/Datepicker.svelte';

	let value;
</script>

<h1>as-date(picker)</h1>

<input type="text" bind:value />
<input type="date" bind:value />
<Datepicker bind:value />
