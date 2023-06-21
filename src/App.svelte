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
		padding: var(--spacingLarge);
		;
		padding: 1em;
		
		margin: 0 auto;
	}
</style>