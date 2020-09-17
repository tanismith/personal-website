<script>
  export let article;
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
      {#each article.tags as tag}{tag}{/each}
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
