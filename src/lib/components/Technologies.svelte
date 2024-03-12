<script lang="ts">
    const images = [
        'ps',
        'lr',
        'pr',
        'ae',
        'ai',
        'xd',
        'vsc',
        'git',
        'figma',
        'html',
        'css',
        'js',
        'php',
        'sql',
        'unity',
        'jquery',
        'react',
        'rails',
        'sass',
        'jekyll',
        'mysql',
        'postgre',
        'svelte',
        'tailwind'
    ];

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