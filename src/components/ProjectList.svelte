<script>
  import { onMount } from "svelte";

  import ProjectItem from "./ProjectItem.svelte";
  export let projects;

  let isMobile;
  onMount(() => {
    isMobile = document.body.clientWidth <= 800;
  });
</script>

<section class="projectsContainer">
  <div class="projectsFlex">
    {#each projects as project, i}
      <ProjectItem
        {project}
        left={isMobile || i % 2 === 0}
        right={isMobile ? false : i % 2 !== 0} />
    {/each}
  </div>
</section>
