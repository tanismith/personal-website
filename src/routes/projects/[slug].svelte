<script context="module">
  export async function preload({ params, query }) {
    // the `slug` parameter is available because
    // this file is called [slug].svelte
    const res = await this.fetch(`projects/${params.slug}.json`);
    const projectsResult = await this.fetch("projects.json");
    const projects = await projectsResult.json();
    const data = await res.json();

    if (res.status === 200) {
      return { post: data, projects };
    } else {
      this.error(res.status, data.message);
    }
  }
</script>

<script>
  import Article from "../../components/Article.svelte";
  export let post;
  export let projects;
</script>

<svelte:head>
  <title>{post.title}</title>
</svelte:head>

<Article article={post} posts={projects} />
