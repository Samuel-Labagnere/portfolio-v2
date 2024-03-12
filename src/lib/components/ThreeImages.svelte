<script lang="ts">
    import Return from "./Return.svelte";
    export let images: ImageArray[] = [];
    export let section: string = '';

    type ImageArray = {
        src: string;
        link: string;
        alt: string;
        title: string;
    };
  
    async function loadImage(src: string) {
      try {
        const { default: image } = await import(`$lib/assets/${section}/${src}.jpg`);
        return image;
      } catch (error) {
        console.error('Error loading image:', error);
        return null;
      }
    }
</script>

<section class="flex flex-col justify-center items-center gap-10 h-screen">
    <Return />

    {#if images.length === 3}
        <div class="flex flex-col md:flex-row w-5/6 md:w-fit mx-5">
            <div>
                <a href={images[0].link} class="relative group">
                    <div class="card">
                        <p>{images[0].title}</p>
                    </div>
                    {#await loadImage(images[0].src) then image}
                        <img src={image} alt={images[1].alt} class="w-full md:w-fit object-cover h-44 md:h-fit border-2 border-white" />
                    {:catch error}
                        <p>Error loading image: {error.message}</p>
                    {/await}
                </a>
        
                <a href={images[1].link} class="relative group ">
                    <div class="card">
                        <p>{images[1].title}</p>
                    </div>
                    {#await loadImage(images[1].src) then image}
                        <img src={image} alt={images[1].alt} class="w-full md:w-fit object-cover h-44 md:h-fit border-2 border-white" />
                    {:catch error}
                        <p>Error loading image: {error.message}</p>
                    {/await}
                </a>
            </div>

            <a href={images[2].link} class="relative group ">
                <div class="card">
                    <p>{images[2].title}</p>
                </div>
                {#await loadImage(images[2].src) then image}
                    <img src={image} alt={images[2].alt} class="w-full md:w-fit object-cover h-44 md:h-fit border-2 border-white" />
                {:catch error}
                    <p>Error loading image: {error.message}</p>
                {/await}
            </a>
        </div>
    {:else}
        <p>Error : Length of images is {images.length}. Length should be 3.</p>
    {/if}
</section>