<script lang="ts">
	import { mainTitle } from '../stores';

	let count: number = 0;
	let title: string = 'initial title';
	const increment = () => {
		count += 1;
	};

	const reset = () => {
		count = 0;
	};

	$: {
		if (count > 10) {
			title = 'too much! (title)';

			mainTitle.update((n) => n + 'too much! (main title)');
		}
	}
</script>

<h1>{title}</h1>
<button on:click={increment}>
	count is {count}
</button>
<button on:click={reset}>Reset</button>

<style>
	h1 {
		color: green;
	}
</style>
