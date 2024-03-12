<script lang="ts">
    import { technologies as images } from "$lib/json/about.json";

    async function loadImage(src: string) {
      try {
        const { default: image } = await import(`$lib/assets/technologies/${src}.svg`);
        return image;
      } catch (error) {
        console.error('Error loading image:', error);
        return null;
      }
    }
</script>

<div class="flex flex-wrap gap-2.5">
    {#each images as image}
        {#await loadImage(image) then svg}
            <img src={svg} alt="" class="w-12" />
        {:catch error}
            <p>Error loading image: {error.message}</p>
        {/await}
    {/each}
</div>