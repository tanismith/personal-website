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

  $: projectsSorted = projects.sort((a, b) => a.order - b.order);
</script>

<svelte:head>
  <title>Tania Smith | UI/UX Designer</title>
</svelte:head>

<PageTitle
  mode="home"
  title="Hi I'm Tania"
  description=" Here you can find some projects I've been working on" />

<ProjectList projects={projectsSorted} />

<PageTitle
  mode=" "
  title=" "
  description="Thank you for visiting and scrolling through my portfolio. <br> If you want to talk
  about any of my projects, or just chat, I'd love to hear from you!" />
