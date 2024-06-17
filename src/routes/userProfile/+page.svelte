<script>
	import userProfile from '$lib/UserProfile.svelte'
	import welcome from '$lib/images/svelte-welcome.webp';
	import welcome_fallback from '$lib/images/svelte-welcome.png';
    import UserProfile from '$lib/UserProfile.svelte';
</script>


<svelte:head>
	<title>My Profile</title>
	<meta name="description" content="My Profile" />
</svelte:head>

<div class="text-column">
	<UserProfile />

	
</div>
