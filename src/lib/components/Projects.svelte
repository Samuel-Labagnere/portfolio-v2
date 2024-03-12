<script lang="ts">
    import projects from "$lib/json/projects.json";
    import Return from "./Return.svelte";
    export let projectSection: string = "";
    export let projectSubSection: string = "";

    async function loadImage(src: string) {
      try {
        const { default: image } = await import(`$lib/assets/${projectSection}/projets/${src}.jpg`);
        return image;
      } catch (error) {
        console.error('Error loading image:', error);
        return null;
      }
    }
</script>

<section class="w-full h-full flex flex-col items-center gap-10 my-5">
    <Return deep={projectSection} />

    {#if projects[projectSection] && projects[projectSection][projectSubSection].length > 0}
        {#each projects[projectSection][projectSubSection] as project}
            {#await loadImage(project.src) then src}
                <img src={src} alt={project.title} class="min-w-96 w-2/3 border-4 border-primary cursor-pointer" />
            {:catch error}
                <p>Error: {error.message}</p>
            {/await}
        {/each}
    {:else}
        <p>Aucun projet dans cette section.</p>
    {/if}
</section>