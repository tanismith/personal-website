<script context="module">
  export async function preload({ params, query }) {
    const projectsResult = await this.fetch("projects.json");
    const projects = await projectsResult.json();
    return { projects };
  }
</script>

<script>
  import PageTitle from "../components/PageTitle.svelte";
  import ProjectList from "../components/ProjectList.svelte";
  export let projects = [];

  const firstProject = "quotes-gallery";

  $: projectsSorted = projects.sort((a) => (a.slug === firstProject ? -1 : 0));
</script>

<svelte:head>
  <title>Tania Smith | UX/UI Developer</title>
</svelte:head>

<PageTitle
  mode="home"
  title="Hi I'm"
  strongTitle="Tania"
  description=" Here you can find some projects I've been working on" />

<ProjectList projects={projectsSorted} />
