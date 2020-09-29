<script context="module">
  export async function preload({ params, query }) {
    // the `slug` parameter is available because
    // this file is called [slug].svelte
    const res = await this.fetch(`blog/${params.slug}.json`);
    const postsResult = await this.fetch("blog.json");
    const posts = await postsResult.json();
    const data = await res.json();

    if (res.status === 200) {
      return { post: data, posts };
    } else {
      this.error(res.status, data.message);
    }
  }
</script>

<script>
  export let post;
  export let posts;
  import Article from "../../components/Article.svelte";
</script>

<style>
  #disqus_thread {
    margin-top: 3em;
  }
</style>

<svelte:head>
  <title>{post.title}</title>
  <script>
    var disqus_config = function () {
      this.page.url = "https://tanismith.com/"; // Replace PAGE_URL with your page's canonical URL variable
      // this.page.identifier = PAGE_IDENTIFIER; // Replace PAGE_IDENTIFIER with your page's unique identifier variable
    };
    (function () {
      // DON'T EDIT BELOW THIS LINE
      var d = document,
        s = d.createElement("script");
      s.src = "https://tanismith-com.disqus.com/embed.js";
      s.setAttribute("data-timestamp", +new Date());
      (d.head || d.body).appendChild(s);
    })();
  </script>
</svelte:head>

<section class="nav-before-after">
  <div class="before">
    <a href="/blog"><i class="fas fa-angle-left" />Back</a>
  </div>
</section>
<Article
  article={post}
  posts={posts.sort((a, b) => new Date(b.date).getTime() - new Date(a.date).getTime())} />
<div class="article-intro">
  <div id="disqus_thread" />
</div>
