<script>
	import { applyAction, enhance } from '$app/forms';
	import '../app.postcss';
	import { currentUser, pb } from '$lib/pocketbase';
</script>

<nav class="bg-neutral text-neutral-content">
	<div class="max-w-[1440px] mx-auto navbar">
		<div class="navbar-start">
			<a href="/" class="btn btn-ghost text-xl">PB + SK</a>
		</div>
		<div class="navbar-end">
			<ul class="menu menu-horizontal">
				{#if $currentUser}
					<li>
						<a href="/">{$currentUser.email}</a>
					</li>
					<li>
						<form
							method="POST"
							action="/logout"
							use:enhance={() => {
								return async ({ result }) => {
									pb.authStore.clear();
									applyAction(result);
								};
							}}
						>
							<button>Log Out</button>
						</form>
					</li>
				{:else}
					<li><a href="/login">Log In</a></li>
					<li><a href="/register">Register</a></li>
				{/if}
			</ul>
		</div>
	</div>
</nav>

<main class="max-w-[1440px] mx-auto py-8 px-4">
	<slot />
</main>
