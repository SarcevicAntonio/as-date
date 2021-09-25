<script>
	import { fade, slide } from 'svelte/transition';
	import MonthGrid from './MonthGrid.svelte';

	export let date = new Date();

	$: yearString = date.getFullYear();

	$: dateString = date.toLocaleString(undefined, {
		weekday: 'short',
		day: 'numeric',
		month: 'short'
	});

	$: monthString = date.toLocaleString(undefined, {
		month: 'long',
		year: 'numeric'
	});
</script>

<div class="popover" transition:slide>
	<button class="year-button">{yearString}</button>
	<span class="date-string">{dateString}</span>
	<div class="flex-sb">
		<button>{'<'}</button>
		<span>{monthString}</span>
		<button>{'>'}</button>
	</div>
	<MonthGrid {date} />
	<div class="flex-sb">
		<button> Cancel </button>
		<button> Today </button>
		<button> Close </button>
	</div>
</div>

<style>
	.popover {
		position: absolute;
		top: 2em;
		left: 50%;
		transform: translateX(-50%);
		width: 15em;
		display: flex;
		flex-direction: column;
	}
	.year-button {
		width: max-content;
	}
	.flex-sb {
		display: flex;
		justify-content: space-between;
		align-items: center;
	}
	.flex-sb * {
		flex-grow: 1;
		text-align: center;
	}
	.date-string {
		font-size: 1.3em;
	}
</style>
