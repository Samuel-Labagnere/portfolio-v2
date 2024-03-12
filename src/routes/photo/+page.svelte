<script lang="ts">
    import ThreeImages from '$lib/components/ThreeImages.svelte';

    let images = [
        { src: 'Mode', link: '/mode', alt: 'Test', title: 'Mode' },
        { src: 'ComingSoon', link: '/voyage', alt: 'Test', title: 'Cooming Soon' },
        { src: 'Portrait', link: '/portrait', alt: 'Test', title: 'Portrait' },
    ];
</script>

<ThreeImages {images} section='photo' />