<script>
  import { each } from "svelte/internal";

  export let project;
</script>

<figure class="gallery-element" data-name={project.title}>
  <a href={project.link} target="_blank">
    <img src={project.image} alt={project.title} width="400" height="280" />
  </a>
  <div class="projectsFlexDescription">
    <a href={project.link} target="_blank">
      <h3>{project.title}</h3>
    </a>
    <p>
      {#if project.technologies}
        {#each project.technologies as tech, i}
          {tech}
          <span>{i === project.technologies.length - 1 ? '' : '+ '}</span>
        {/each}
      {/if}

      <br />
      {#if project.tools}
        {#each project.tools as tool, i}
          {tool}
          <span>{i === project.tools.length - 1 ? '' : '+'}</span>
        {/each}
      {/if}
    </p>
    <article>{project.shortDescription}</article>
    <a href={project.link}>See more</a>
  </div>
</figure>
