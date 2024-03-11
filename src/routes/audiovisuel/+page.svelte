<script lang="ts">
    import ThreeImages from '$lib/components/ThreeImages.svelte';

    let images = [
        { src: 'Métrages', link: '/', alt: 'Test', title: 'Métrages' },
        { src: 'Autres', link: '/', alt: 'Test', title: 'Autres' },
        { src: 'VLOGs', link: '/', alt: 'Test', title: 'VLOGs' },
    ];
</script>

<ThreeImages {images} section='audiovisuel' />