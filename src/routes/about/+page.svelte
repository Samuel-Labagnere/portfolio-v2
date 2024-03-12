<script lang="ts">
    import Return from "$lib/components/Return.svelte";
    import sam from "$lib/assets/sam.jpg";
    import linkedin from '$lib/assets/linkedin.svg';
    import instagram from '$lib/assets/instagram.svg';
    import github from '$lib/assets/github.svg';
    import Technologies from "$lib/components/Technologies.svelte";
    import global from "$lib/json/global.json";
    import about from "$lib/json/about.json";
</script>


<section class="flex flex-col-reverse md:block my-10">
    <Return />

    <div class="relative w-full h-full">
        <div class="md:grid grid-cols-2">
            <img src={sam} alt="Samuel Labagnere" class="mx-auto col-start-2" />
        </div>
    
        <div class="grid md:grid-cols-2 md:absolute top-0 left-0 p-12 md:p-16 gap-y-10">
            <div class="flex flex-col gap-5 w-full">
                <div class="uppercase">
                    <h1 class="text-3xl font-semibold">Samuel<br />Labagnere</h1>
                    <h2 class="text-xl italic">{global.title}</h2>
                </div>
    
                {#each about.description as description}
                    <p class="text-lg italic">
                        {@html description}
                    </p>
                {/each}

                <Technologies />
            </div>
    
            <div class="flex justify-end items-end">
                <a href="https://www.linkedin.com/in/samuel-labagnere/" target="_blank">
                    <img alt="Linkedin" src={linkedin} />
                </a>
                <a href="https://www.instagram.com/samuel.labagnere/" target="_blank">
                    <img alt="Instagram" src={instagram} />
                </a>
                <a href="https://github.com/Samuel-Labagnere/" target="_blank">
                    <img alt="Github" src={github} />
                </a>
            </div>
        </div>
    </div>
</section>