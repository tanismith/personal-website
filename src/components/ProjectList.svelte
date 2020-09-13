<script>
    import ProjectItem from './ProjectItem.svelte'
    export let projects
</script>

<section class="projectsContainer">
    <div class="projectsFlex">
        {#each projects as project, i}
            <ProjectItem {project} left={i % 2 === 0} right={i % 2 !== 0} />
        {/each}
    </div>
</section>
