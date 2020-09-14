<script>
  //TODO fix responsive
  export let currentPage;
  let active = false;

  $: if (currentPage || currentPage === undefined) {
    active = false;
  }
</script>

<style>
  .is-active {
    border-bottom: 2px solid #53b6b0;
  }

  /* Estilos del header */
  header {
    height: 80px;
    padding: 15px 25px;
  }

  header #menuIcon {
    display: none;
  }

  header a {
    color: var(--color-text);
  }

  .header a:hover {
    color: var(--color-title);
  }

  /* Aqui terminan estilos del header */

  /* Estilos del nav */
  nav {
    height: inherit;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-between;
  }

  header nav ul {
    display: flex;
    align-items: baseline;
    margin-right: 1rem;
  }

  header nav ul li {
    list-style: none;
    padding-right: 10px;
  }

  nav ul a,
  .nav-active a {
    position: relative;
    z-index: 99;
    justify-content: center;
    font-family: var(--texts-font);
    color: var(--color-text);
    font-size: 16px;
    transition: all 0.4;
    margin: 0 1rem;
  }

  .nav-active a {
    color: var(--color-title);
    margin: 0;
  }

  nav ul a:hover:before,
  .nav-active a:hover:before {
    width: 100%;
    transition: all 0.4s;
    opacity: 1;
  }

  nav ul a:before,
  .nav-active a:before {
    position: absolute;
    content: "";
    width: 0;
    bottom: -5px;
    border-bottom: 2px solid #53b6b0;
    color: var(--color-title);
    opacity: 0;
  }

  nav svg {
    margin: -30px;
  }

  .nav-active {
    display: none;
  }

  .message-icon {
    position: absolute;
    bottom: 0;
    padding: 0 6px;
    width: 25px;
    height: auto;
  }

  /* Aqui terminan estilos del nav */
  @media screen and (max-width: 800px) {
    /* Empiezan estilos del header */
    header {
      position: fixed;
      background-color: white;
      width: 100%;
      height: 50px;
      z-index: 999;
    }

    /* Aqui terminan estilos del header */
    /* Estilos del nav */
    header #menuIcon {
      display: block;
      z-index: 3;
    }

    .nav {
      background-color: rgba(206, 240, 240, 0.906);
      display: flex;
      flex-direction: column;
      position: absolute;
      z-index: 1;
      top: 0;
      right: -100%;
      width: 100%;
      height: 100vh;
      justify-content: center;
      align-items: center;
      transition: 0.5s;
    }

    .nav-active {
      background-color: rgba(206, 240, 240, 0.906);
      display: flex;
      flex-direction: column;
      position: absolute;
      z-index: 1;
      top: 0;
      right: 0;
      width: 100%;
      height: 100vh;
      justify-content: center;
      align-items: center;
    }

    header .navbar {
      width: 90%;
      align-items: flex-start;
    }

    header nav ul {
      display: none;
    }
    header nav ul li {
      padding: 10px 0;
    }

    nav {
      display: flex;
      flex-direction: row;
    }

    nav svg {
      padding-left: 1em;
      margin-top: -50px;
      width: 60%;
    }
  }
</style>

<header>
  <nav class="navbar">
    <section>
      <!-- <img src="assets/logo.svg" alt="tani smith" width="150px" height="auto"> -->
      <a href="/">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          xmlns:xlink="http://www.w3.org/1999/xlink"
          width="200"
          height="142"
          viewBox="0 0 367 142">
          <defs>
            <clipPath id="clip-logo">
              <rect width="367" height="142" />
            </clipPath>
          </defs>
          <g id="logo" clip-path="url(#clip-logo)">
            <path
              id="Path_48"
              data-name="Path 48"
              d="M45.54.513c21.824,0,19.7,16.743,35.207,31.7s29.213,9.979,36.314,33.007c7.618,33-20.765,53.8-55.026,53.8S0,92.233,0,59.2,11.279.513,45.54.513Z"
              transform="translate(8 12.702)"
              fill="#14b7ae" />
            <text
              id="t"
              transform="translate(42 108)"
              fill="#fff"
              font-size="100"
              font-family="SourceSansPro-Semibold, Source Sans Pro"
              font-weight="600">
              <tspan x="-18.15" y="0">t</tspan>
            </text>
            <text
              id="s"
              transform="translate(85 109)"
              fill="#fff"
              font-size="100"
              font-family="SourceSansPro-Semibold, Source Sans Pro"
              font-weight="600">
              <tspan x="-21.6" y="0">s</tspan>
            </text>
            <text
              id="mith."
              transform="translate(126.156 13.435)"
              fill="#00aaa1"
              font-size="100"
              font-family="SourceSansPro-Semibold, Source Sans Pro"
              font-weight="600">
              <tspan x="0" y="102">mith.</tspan>
            </text>
          </g>
        </svg></a>
    </section>
    <ul class="nav" class:nav-active={active}>
      <li><a class:is-active={!currentPage} href=".">Portfolio</a></li>
      <li>
        <a class:is-active={currentPage === 'about'} href="about">About</a>
      </li>
      <li>
        <a
          rel="prefetch"
          class:is-active={currentPage === 'blog'}
          href="blog">Blog</a>
      </li>
      <li>
        <a href="mailto:hola@tanismith.com">Say hi <img class="message-icon" src="/images/icon-message.png" alt="message-icon" />
        </a>
      </li>
    </ul>
    <a id="menuIcon" on:click={() => (active = !active)}>
      <i class="fas fa-bars" />
    </a>
  </nav>
</header>
