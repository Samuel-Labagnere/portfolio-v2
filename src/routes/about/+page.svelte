<script lang="ts">
    import Return from "$lib/components/Return.svelte";
    import sam from "$lib/assets/sam.jpg";
    import linkedin from '$lib/assets/linkedin.svg';
    import instagram from '$lib/assets/instagram.svg';
    import github from '$lib/assets/github.svg';
    import opquast from '$lib/assets/opquast.svg';
    import Technologies from "$lib/components/Technologies.svelte";
    import global from "$lib/json/global.json";
    import about from "$lib/json/about.json";
</script>


<section class="flex flex-col md:block my-10">
    <Return />

    <div class="relative flex flex-col-reverse md:block w-full h-full bg-black/40">
        <div class="md:grid grid-cols-2">
            <img src={sam} alt="Samuel Labagnere" class="absolute md:block top-0 right-0 -z-10 mx-auto col-start-2" />
        </div>
    
        <div class="grid md:grid-cols-2 md:absolute top-0 left-0 p-12 md:p-16 gap-y-10">
            <div class="relative flex flex-col gap-5 w-full">
                <div class="uppercase">
                    <div class="flex gap-5 md:justify-between ">
                        <h1 class="text-3xl font-semibold">Samuel<br />Labagnere</h1>
                        <a href={about.opquast} target="_blank">
                            <img src={opquast} alt="Opquast niveau avancé" class="w-24" />
                        </a>
                    </div>

                    <h2 class="text-xl italic">{global.title}</h2>
                </div>
    
                {#each about.description as description}
                    <p class="text-lg italic">
                        {@html description}
                    </p>
                {/each}

                <Technologies />
            </div>
    
            <div class="flex justify-center md:justify-end items-end gap-6">
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