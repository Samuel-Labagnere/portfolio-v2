<script lang="ts">
    import projects from "$lib/json/projects.json";
    import Overlay from "./Overlay.svelte";
    import Return from "./Return.svelte";
    export let projectSection: string;
    export let projectSectionName: string;
    export let projectSubSection: string;

    let currentProjects = projects[projectSection][projectSubSection] as {
        src: string;
        title: string;
        description: string[];
        info: (string | string[])[];
        link: string;
    }[] | undefined;

    async function loadImage(src: string) {
      try {
        const { default: image } = await import(`$lib/assets/${projectSection}/projets/${src}.jpg`);
        return image;
      } catch (error) {
        console.error('Error loading image:', error);
        return null;
      }
    }

    let active: { [key: string]: boolean } = {};
    $: if (currentProjects) {
        for (const project of currentProjects) {
            active[project.src] = false;
        }
    }

    console.log(active);

    const setActive = (src: string) => {
        active[src] = true;
        console.log(active);
    }
</script>

<section class="w-full h-full flex flex-col items-center gap-5 my-5">
    <Return deep={projectSection} />

    {#if currentProjects && currentProjects?.length > 0}
        {#each currentProjects as project}
            {#await loadImage(project.src) then src}
                <img src={src} alt={project.title} class="min-w-96 w-2/3 border-4 border-primary cursor-pointer"
                on:click={() => setActive(project.src)}  />
                <Overlay project={project} section={projectSection} sectionName={projectSectionName} active={active} />
            {:catch error}
                <p>Error: {error.message}</p>
            {/await}
        {/each}
    {:else}
        <p>Aucun projet dans cette section.</p>
    {/if}
</section>