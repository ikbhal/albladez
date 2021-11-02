<script>
	import About from './About.svelte';
	import Videos from './Videos.svelte';
	import Contact from './Contact.svelte';
	import LikeButton from './LikeButton.svelte';
	import Comments from './Comments.svelte';


	import Profile from './Profile.svelte';
    import Todos from './Todos.svelte';

    import { auth, googleProvider } from './firebase';
    import { authState } from 'rxfire/auth';

    let user;

    const unsubscribe = authState(auth).subscribe(u => user = u);

    function login() {
        auth.signInWithPopup(googleProvider);
    }
</script>

<main>


	
<section>
	{#if user}
		<Profile {...user} />
		<button on:click={ () => auth.signOut() }>Logout</button>
		<hr>
		<Todos uid={user.uid} />
	{:else}
		<button on:click={login}>
			Signin with Google
		</button>
	{/if}
	</section>
	
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