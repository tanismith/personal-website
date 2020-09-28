<script>
  import PageTitle from "../components/PageTitle.svelte";
</script>

<style>
  .about {
    margin: 2em auto 0;
  }

  .items-box {
    display: flex;
    width: 60%;
    margin: 4em auto 0;
    justify-content: space-around;
  }
  .item {
    display: flex;
    flex-direction: column;
    width: 35%;
    align-items: center;
  }
  .item img {
    width: 100px;
  }
  .item h2 {
    color: var(--color-title);
    font-size: var(--subtitle-font-size);
    font-family: var(--title-font);
    margin-top: 20px;
    font-weight: 600;
  }
  .item p {
    font-family: var(--texts-font);
    font-weight: 200;
    font-size: var(--text-font-size);
    color: var(--color-text);
    text-align: center;
  }
</style>

<PageTitle mode="home" title="Hi there," description="" />
<div class="about">
  <div class="aboutDescription">
    <p>
      My name is Tania, I enjoy building digital products and working in
      projects wich are challenging. I move from concepts and sketches, to
      wireframes and prototypes, to high fidelity UI/UX designs.<br /><br /> With
      my work I hope to simplify user's everyday lives with a beautiful user experience.
      One of my pillars for creating solutions is the perspective of self-reflection
      and investigation accompanied by artistic sensitivity. <br /><br /> A little
      more about me <br />My personal experiences have taught me a few things
      about myself: I enjoy the process of constantly educate myself, readjust
      and train to be a better person. I work daily to form positive habits. I'm
      always looking for new and better ways to solve problems.
    </p>
    <!-- <img src="/images/about.jpg" alt="tania-smith-senmache" /> -->
  </div>
</div>
<div class="items-box">
  <div class="item">
    <img src="/images/bubble-icon.webp" alt="bubble icon" />
    <h2>Designer</h2>
    <p>
      I'm interested in ways to close gaps, to be more inclusive, accessible and
      humane raising awareness in the creation of designs focused on the needs
      of users.
    </p>
  </div>
  <div class="item">
    <img src="/images/builder-icon.webp" alt="bubble icon" />
    <h2>Builder</h2>
    <p>
      I love moving from design to implementing interactive experiences on the
      web, bringing ideas to life with meticulous care and attention to detail.
    </p>
  </div>
</div>
