<script>
  export let project;
  export let left = true;
  export let right = false;

  $: target = project.link ? "_blank" : "_self";
</script>

<figure class="gallery-element" data-name={project.title}>
  {#if left}
    <div class="image">
      <a href={project.link || `projects/${project.slug}`} {target}>
        <img src={project.thumb} alt={project.title} />
      </a>
    </div>
  {/if}

  <div class="projectsFlexDescription">
    <a href={project.link || `projects/${project.slug}`} target="_self">
      <h2>{project.title}</h2>
    </a>
    <p>
      {#if project.tags}
        {#each project.tags as tech, i}
          {tech}
          <span>{i === project.tags.length - 1 ? '' : '+ '}</span>
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
    <article>{project.overview}</article>
    <a href={project.link || `projects/${project.slug}`}>See more</a>
  </div>
  {#if right}
    <div class="image">
      <a href={project.link || `projects/${project.slug}`} {target}>
        <img src={project.thumb} alt={project.title} />
      </a>
    </div>
  {/if}
</figure>
