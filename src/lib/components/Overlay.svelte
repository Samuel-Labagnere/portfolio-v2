<script lang="ts">
    export let project: Project;
    export let section: string;
    export let sectionName: string;
    export let active: { [key: string]: boolean };

    type Project = {
        src: string;
        title: string;
        description: string[];
        info: (string | string[])[];
        link: string;
    };

    async function loadImage(src: string) {
        try {
            const { default: image } = await import(`$lib/assets/${section}/projets/${project.src}.jpg`);
            return image;
        } catch (error) {
            console.error('Error loading image:', error);
            return null;
        }
    }

    const close = () => {
        active[project.src] = false;
    }
</script>

<div class="{active[project.src] ? 'block' : 'hidden'} fixed top-0 left-0 w-screen h-screen overflow-y-scroll bg-primary text-black p-8">
    <div class="flex flex-col gap-5">
        <div class="relative flex flex-col lg:flex-row gap-5">
            {#await loadImage(project.src) then src}
                <img src={src} alt={project.title} class="max-h-[75vh] md:max-w-[50vw] border border-black object-cover" />
            {:catch error}
                <p>Error loading image: {error.message}</p>
            {/await}

            <button on:click={() => close()} class="closing-tag"></button>

            <div class="flex flex-col gap-20">
                <div>
                    <p class="text-7xl font-bold">{sectionName}</p>
                    <p class="text-4xl font-semibold">{@html project.title}</p>
                </div>

                <div class="flex flex-col gap-2.5 lg:gap-5">
                    {#each project.description as description}
                        <p>{@html description}</p>
                    {/each}
                </div>
            </div>
        </div>

        <div class="flex justify-between">
            <div class="font-semibold">
                {#each project.info as info}
                    {#if typeof info === typeof []}
                        <p>{info[0]} : {info[1]}</p>
                    {:else}
                        <p>{info}</p>
                    {/if}
                {/each}
            </div>

            <a href={project.link ?? '#'} class="btn overlay 
            {project.link ? '!text-black' : 'disabled-link'}" target="_blank">
                {project.link ? 'Ouvrir' : 'Indisponnible'}
            </a>
        </div>
    </div>
</div>