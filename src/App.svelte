<script>
	
	import Library from "./Library/library.svelte";
	import Detail from "./detail/Detail.svelte";

	let page = 'detail';
	let pageArgs = {id: 3};
	function handleBookSelect(event){
		page = 'detail';
		pageArgs = event.detail;
	}

</script>

<main>
<!-- <Library on:book-select={handleBookSelect}/> -->

{#if page === 'detail'}
	<Detail {...pageArgs}/>
	{:else}
	<Library on:book-select={handleBookSelect}/>
	{/if}

</main>
<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>