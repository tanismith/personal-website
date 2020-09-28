<script>
  let showBackToTop = false;

  async function handleBackToTop() {
    window.scrollTo({ top: 0, left: 0, behavior: "smooth" });
  }
</script>

<style>
  footer {
    position: relative;
    margin-bottom: 2em;
  }
  .top {
    position: fixed;
    bottom: 2em;
    right: 1em;
    background: rgb(0, 170, 161, 0.8);
    padding: 5px 10px;
    color: white;
    font-size: 25px;
    border-radius: 8px;
    cursor: pointer;
  }
</style>

<svelte:window
  on:scroll={() => {
    const top = window.pageYOffset || document.documentElement.scrollTop;
    if (top > 200) {
      showBackToTop = true;
    } else {
      showBackToTop = false;
    }
  }} />

<footer>
  <section>
    <p>Connect with me at</p>
    <hr />
  </section>
  <section>
    <a href="https://www.linkedin.com/in/tania-smith-senmache">
      <i class="fab fa-linkedin-in" /></a>
    <a href="https://github.com/tanismith"> <i class="fab fa-github" /></a>
    <a href="https://codepen.io/t4n1a/pens/showcase">
      <i class="fab fa-codepen" /></a>
  </section>
  {#if showBackToTop}
    <section
      on:click={handleBackToTop}
      class="top"
      id="backTop"
      title="Go to top on">
      <i class="fas fa-arrow-up" />
    </section>
  {/if}
</footer>
