<script lang="ts">
    import ThreeImages from '$lib/components/ThreeImages.svelte';

    let images = [
        { src: 'Mode', link: '/', alt: 'Test', title: 'Mode' },
        { src: 'ComingSoon', link: '/', alt: 'Test', title: 'Cooming Soon' },
        { src: 'Portrait', link: '/', alt: 'Test', title: 'Portrait' },
    ];
</script>

<ThreeImages {images} section='photo' />