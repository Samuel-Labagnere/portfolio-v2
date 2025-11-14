<script lang="ts">
    import ThreeImages from '$lib/components/ThreeImages.svelte';

    let images = [
        { src: 'Mode', link: '/outdoor', alt: 'Test', title: 'Extérieur' },
        { src: 'ComingSoon', link: '/voyage', alt: 'Test', title: 'Cooming Soon' },
        { src: 'Portrait', link: '/studio', alt: 'Test', title: 'Studio' },
    ];
</script>

<ThreeImages {images} section='photo' />
