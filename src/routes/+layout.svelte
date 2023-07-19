<nav>
	<div class="nav__container">
		<a href="/" class="nav-logo" title="back to Homepage">Hafus</a>
		<div class="nav-links">
			{#each nav as link}
				{#if link.isShow}
					<a href={link.href} class="link">{link.title}</a>
				{/if}
			{/each}
		</div>
	</div>
</nav>

<div class="container">
	<slot></slot>
</div>

<script>
	const nav = [
		{
			title: "About",
			href: "/about",
			isShow: true, 
		},
		{
			title: "Blog",
			href: "/blog",
			isShow: true, 
		},
		{
			title: "Portfolio",
			href: "/project",
			isShow: true, 
		},
		{
			title: "Contacts",
			href: "/conatcts",
			isShow: true, 
		},
		{
			title: "temp",
			href: "/temp",
			isShow: false, 
		},
	]
</script>

<style>
	.container {
		max-width: 1400px;
		margin: 50px auto;
	}
</style>
