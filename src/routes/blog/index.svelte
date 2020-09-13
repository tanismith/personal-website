<script context="module">
    export function preload({ params, query }) {
        return this.fetch(`blog.json`)
            .then((r) => r.json())
            .then((posts) => {
                return { posts }
            })
    }
</script>

<script>
    export let posts
</script>

<svelte:head>
    <title>Blog</title>
</svelte:head>

<ul>
    <section class="title-page-container">
        <span>Writting</span>
        <hr />
        <p>I love sharing some thoughts, tips and practical information. <br />Here you have a collection of posts.</p>
    </section>
    <section class="gallery-blogs-container">
        {#each posts as post}
            <div class="post-container">
                <a href="blog/{post.slug}">
                    <img src={post.img} alt="Vormet website" />
                    <h3>
                        {#each post.tags as tag}{tag}{/each}
                    </h3>
                    <h2>{post.title}</h2>
                    <hr />
                    <small>{new Date(post.date).toLocaleDateString()}</small>
                    <p>{post.overview}</p>
                </a>
                <a href="blog/{post.slug}">Read more</a>
            </div>
        {/each}
    </section>
    {#each posts as post}
        <!-- we're using the non-standard `rel=prefetch` attribute to
				tell Sapper to load the data for the page as soon as
				the user hovers over the link or taps it, instead of
				waiting for the 'click' event -->
        <li><a rel="prefetch" href="blog/{post.slug}">{post.title}</a></li>
    {/each}
</ul>
