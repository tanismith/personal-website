<script>
    export let article
</script>

<section class="article-description">
    <div>
        <h1>{article.title}</h1>
        <hr />
        <h3>
            {#each article.tags as tag}{tag}{/each}
        </h3>
        {#if article.date}<small>{new Date(article.date).toLocaleDateString()}</small>{/if}
        <p>{article.intro || article.overview}</p>
    </div>
    <img src={article.img || article.thumb} alt={article.title} width="400" height="400" />
</section>
<hr class="divider" />
<section class="article-intro">
    <article>
        {@html article.html}
    </article>
</section>
