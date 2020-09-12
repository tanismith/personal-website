<script>
  import ProjectItem from "./ProjectItem.svelte";
  export let projects;
</script>

<section class="projectsContainer">
  <div class="projectsFlex">
    {#each projects as project}
      <ProjectItem {project} />
    {/each}
  </div>
</section>
