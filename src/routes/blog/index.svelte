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
    import PageTitle from '../../components/PageTitle.svelte'
</script>

<svelte:head>
    <title>Blog</title>
</svelte:head>

<PageTitle
    title="Writting"
    strongTitle=""
    description="I love sharing some thoughts, tips and practical information. <br> Here you have a collection of posts."
    mode="home" />

<section class="gallery-blogs-container">
    {#each posts as post}
        <div class="post-container">
            <a rel="prefetch" href="blog/{post.slug}">
                <img src={post.thumb} alt="Vormet website" />
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
