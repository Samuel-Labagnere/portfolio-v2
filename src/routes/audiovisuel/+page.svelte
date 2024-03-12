<script lang="ts">
    import ThreeImages from '$lib/components/ThreeImages.svelte';

    let images = [
        { src: 'Métrages', link: '/metrages', alt: 'Test', title: 'Métrages' },
        { src: 'Autres', link: '/autres', alt: 'Test', title: 'Autres' },
        { src: 'VLOGs', link: '/vlogs', alt: 'Test', title: 'VLOGs' },
    ];
</script>

<ThreeImages {images} section='audiovisuel' />