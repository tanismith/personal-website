<script>
  import Nav from "../components/Nav.svelte";
  import Container from "../components/Container.svelte";
  import Footer from "../components/Footer.svelte";

  export let segment;
</script>

<Nav currentPage={segment} />

<main>
  <Container>
    <slot />
  </Container>
  <section class="madeBy">
    <p>Handcrafted with ❤ by Tani</p>
  </section>
</main>
<Footer />
