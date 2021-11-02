<script>
	import About from './About.svelte';
	import Videos from './Videos.svelte';
	import Contact from './Contact.svelte';
	import LikeButton from './LikeButton.svelte';
	import Comments from './Comments.svelte';
</script>

<main>
	<About/>
	<LikeButton/>
	<Videos/>
	<hr/>
	<Comments/>
	<Contact/>
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