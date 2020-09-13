<script context="module">
    export async function preload({ params, query }) {
        const projectsResult = await this.fetch('projects.json')
        const projects = await projectsResult.json()

        return {
            projects: projects.sort((a, b) => new Date(b.date).getTime() - new Date(a.date).getTime()),
        }
    }
</script>

<script>
    import PageTitle from '../components/PageTitle.svelte'
    import ProjectList from '../components/ProjectList.svelte'
    export let projects = []
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
