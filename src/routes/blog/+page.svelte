<svelte:head>
	<title>My Blog</title>
</svelte:head>

<div class="contatiner"> 
	<h1>Blog</h1>
	<div class="blogposts">
		{#each routes as page }
			<div class="post">
				<h2>{page.title}</h2>
				<p>{page.body}</p>
				<p class="readmore">
					<a class="link" href={`/blog/posts/${page.id}`}>Read more</a>
				</p>
			</div>
		{/each}
	</div>
</div>


<script>
	import {routes} from './routes.js'
</script>

<style>
	.contatiner {
		margin: 50px auto;
		max-width: 800px;
		padding: 0 20px;
	}

	.blogposts {
		display: grid;
		grid-template-columns: 1fr 1fr;
		grid-gap: 20px;
	}

	.post {
		border: 1px solid #ddd;
		padding: 10px;
		box-shadow: 0 0 10px #eee;

	}

	.link {
		color: rgb(10, 10, 139)
	}
</style>
