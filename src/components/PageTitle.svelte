<script>
  export let mode;
  export let title;
  export let description;
</script>

<div class="title-page-container">
  {#if mode === 'home'}
    <h1>{title}</h1>
  {/if}
  <hr />
  {#if description}
    <p>
      {@html description}
    </p>
  {/if}
</div>
