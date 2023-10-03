<script>
	import { onMount } from 'svelte';

	let auth2;

	onMount(() => {
		const script = document.createElement('script');
		script.src = 'https://apis.google.com/js/platform.js';
		script.onload = () => {
			gapi.load('auth2', () => {
				auth2 = gapi.auth2.init({
					client_id: 'YOUR_CLIENT_ID'
				});
			});
		};
		document.head.appendChild(script);
	});

	function signIn() {
		auth2.signIn().then((googleUser) => {
			const id_token = googleUser.getAuthResponse().id_token;
			// Now you can send the id_token to your server to validate and authenticate the user
		});
	}

	function signOut() {
		auth2.signOut().then(() => {
			console.log('User signed out.');
		});
	}
</script>

<button on:click={signIn}>Sign In with Google</button>
<button on:click={signOut}>Sign Out</button>
