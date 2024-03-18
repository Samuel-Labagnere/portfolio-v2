<script lang="ts">
    import ThreeImages from '$lib/components/ThreeImages.svelte';

    let images = [
        { src: 'ProjetsUniversitaires', link: '/universitaires', alt: 'Test', title: 'Projets Universitaires' },
        { src: 'ProjetsProfessionnels', link: '/professionnels', alt: 'Test', title: 'Projets Professionnels' },
        { src: 'ProjetsPersonnels', link: '/personnels', alt: 'Test', title: 'Projets Personnels' },
    ];
</script>

<ThreeImages {images} section='web' />