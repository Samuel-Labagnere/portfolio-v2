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

<div class="flex flex-wrap gap-2.5 items-center">
    {#each images as image}
        {#await loadImage(image[0]) then svg}
          <a href={image[1]} target="_blank">
            <img src={svg} alt="" class="w-12" />
          </a>
        {:catch error}
            <p>Error loading image: {error.message}</p>
        {/await}
    {/each}
</div>