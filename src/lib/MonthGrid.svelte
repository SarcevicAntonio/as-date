<script lang="ts">
	export let date: Date;

	$: daysInMonth = new Date(date.getFullYear(), date.getMonth() - 1, 0).getDate();

	$: firstWeekday = new Date(date.getFullYear(), date.getMonth(), 1).getDay();
</script>

<div class="grid">
	{#each ['S', 'M', 'T', 'M', 'T', 'F', 'S'] as item}
		<span>
			{item}
		</span>
	{/each}
	{#each new Array(firstWeekday) as _}
		<span />
	{/each}
	{#each new Array(daysInMonth) as item, i}
		<button>{i + 1}</button>
	{/each}
</div>

<style>
	.grid {
		display: grid;
		grid-template-columns: repeat(7, 1fr);
	}
	span {
		text-align: center;
	}
</style>
