<script lang="ts">
    import ThreeImages from '$lib/components/ThreeImages.svelte';

    let images = [
        { src: 'ProjetsUniversitaires', link: '/', alt: 'Test', title: 'Projets Universitaires' },
        { src: 'ComingSoon', link: '/', alt: 'Test', title: 'Projets Professionnels' },
        { src: 'ProjetsPersonnels', link: '/', alt: 'Test', title: 'Projets Personnels' },
    ];
</script>

<ThreeImages {images} section='jeux' />