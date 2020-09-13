<script>
    export let mode
    export let title
    export let strongTitle
    export let description
</script>

<div class="title-page-container">
    {#if mode === 'home'}
        <span>{title}</span>
        <h1>{strongTitle}</h1>
    {/if}
    <hr />
    {#if description}
        <p>
            {@html description}
        </p>
    {/if}
</div>
