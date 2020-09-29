<script>
  export let previous;
  export let next;
  export let type = "projects";
</script>

<section class="article-intro">
  <hr class="divider" />
  <section class="nav-before-after">
    <div class="before">
      <a href="/{type}/{previous.slug} "><i
          class="fas fa-angle-left" />Previus</a>
    </div>
    <div class="after">
      <a href="/{type}/{next.slug}">Next<i class="fas fa-angle-right" /></a>
    </div>
  </section>
</section>
