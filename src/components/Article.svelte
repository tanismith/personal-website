<script>
  export let article;
  export let posts;
  import BackNextControls from "../components/BackNextControls.svelte";

  $: currentPostIndex = posts.findIndex((p) => article.slug === p.slug);
  $: type = article.order ? "projects" : "blog";

  $: next = article.order
    ? posts.find((p) => p.order === article.order + 1) ||
      posts.find((p) => p.order === 1)
    : posts[currentPostIndex + 1] || posts[0];

  $: previous = article.order
    ? posts.find((p) => p.order === article.order - 1) ||
      posts.find((p) => p.order === posts.length)
    : posts[currentPostIndex - 1] || posts[posts.length - 1];
</script>

<style>
  :global(.article-intro article img) {
    max-width: 100%;
    text-align: center;
  }
</style>

<section class="article-description">
  <div>
    <h1>{article.title}</h1>
    <hr />
    <h2>
      {#each article.tags as tag}+ {tag}{/each}
    </h2>
    {#if article.date}
      <small>{new Date(article.date).toLocaleDateString()}</small>
    {/if}
    <p>
      {@html article.intro || article.overview}
    </p>
  </div>
  <img src={article.img || article.thumb} alt={article.title} />
</section>
<hr class="divider" />
<section class="article-intro">
  <article>
    {@html article.html}
  </article>
</section>
<BackNextControls {type} {next} {previous} />
