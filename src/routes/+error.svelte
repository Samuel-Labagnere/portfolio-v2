<script>
	import { page } from '$app/stores';
    console.log($page?.error);
</script>

<section class="flex flex-col items-center justify-center w-screen h-screen">
    <h1 class="text-4xl font-bold">{$page?.error?.message}</h1>
    <p class="italic">Oups, il semblerait que vous ayez rencontré une erreur</p>

    <a href="/" class="btn-link my-5">&lt; Accueil</a>
</section>