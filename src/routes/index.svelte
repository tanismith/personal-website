<script>
  import PageTitle from "../components/PageTitle.svelte";
  import ProjectList from "../components/ProjectList.svelte";
  let projects = [
    {
      title: "Quotes-Gallery",
      image: "/images/quotes-gallery.png",
      link: "https://quote-gallery.netlify.app/",
      tools: ["Adobe XD"],
      technologies: ["CSS Grid", "Responsive"],
      shortDescription:
        "This is a short description of this project and has a fewlines explaining about it.",
    },
    {
      title: "Blog Parvularia",
      image: "/images/Blog-parvularia.png",
      link: "https://tanismith.github.io/blog-template/",
      tools: ["HTML + CSS"],
      technologies: ["CSS Grid", "Responsive"],
      shortDescription:
        "This is a short description of this project and has a fewlines explaining about it.",
    },
    {
      title: "Game Shelf Landing",
      image: "/images/GameShelf.png",
      link: "https://game-shelf.esteban.site/",
      tools: ["Figma"],
      technologies: ["CSS Grid", "Responsive"],
      shortDescription:
        "This is a short description of this project and has a fewlines explaining about it.",
    },
    {
      title: "CSS Cloud",
      image: "/images/Cloud.png",
      link: "https://codepen.io/t4n1a/pen/yLeeZyX",
      tools: ["Codepen"],
      shortDescription:
        "This is a short description of this project and has a fewlines explaining about it.",
    },
    {
      title: "Google site Clon",
      image: "/images/googleClon.png",
      link: "https://tanismith.github.io/googleClon/",
      tools: ["HTML, CSS"],
      technologies: ["CSS Grid", "Responsive"],
      shortDescription:
        "This is a short description of this project and has a fewlines explaining about it.",
    },
    {
      title: "Dancing School",
      image: "/images/escuela de danza.png",
      link: "https://www.frentededanzaindependiente.com/",
      tools: ["Design"],
      shortDescription:
        "This is a short description of this project and has a fewlines explaining about it.",
    },
  ];
</script>

<svelte:head>
  <title>Tania Smith | Front End Web Developer</title>
</svelte:head>

<PageTitle
  mode="home"
  title="Hi I'm"
  strongTitle="Tania"
  description=" Here you can find some projects I've been working on" />

<ProjectList {projects} />
