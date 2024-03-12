<svelte:head>
  <title>Portfolio | Samuel Labagnere</title>
</svelte:head>

<script lang="ts">
  import logo from '$lib/assets/logo.png';
  import sam from '$lib/assets/sam.jpg';
  import linkedin from '$lib/assets/linkedin.svg';
  import instagram from '$lib/assets/instagram.svg';
  import github from '$lib/assets/github.svg';
  import global from "$lib/texts/global.json";
</script>

<section class="h-screen overflow-y-hidden">
  <header class="flex flex-col items-center">
    <img alt="Logo de Samuel Labagnere" src={logo} class="w-20" />
    <div class="flex flex-col items-center uppercase">
      <h1 class="text-2xl">Samuel Labagnere</h1>
      <h2 class="text-lg">{global.title}</h2>
    </div>
  </header>
  
  <section class="relative">
    <div class="absolute flex flex-col justify-center gap-2.5 md:flex-row md:justify-around items-center w-full h-full">
      <div class="flex flex-col gap-2.5 items-center">
        <a href="/photo" class="btn">
          Photo
        </a>
  
        <a href="/audiovisuel" class="btn">
          Audiovisuel
        </a>
      </div>
  
      <div class="flex flex-col gap-2.5 items-center">
        <a href="/web" class="btn">
          Web
        </a>
  
        <a href="/jeux" class="btn">
          Jeux vidéo
        </a>
      </div>

      <a href="/" class="md:hidden btn">
        À propos
      </a>
    </div>

    <img alt="Samuel Labagnere en costume" src={sam} class="mx-auto" />

    <div class="absolute bottom-0 flex justify-center items-center w-full my-12 md:my-5 gap-6">
      <a href="/about" class="hidden md:block link">
        À propos
      </a>

      <a href="https://www.linkedin.com/in/samuel-labagnere/" target="_blank">
        <img alt="Linkedin" src={linkedin} />
      </a>
      <a href="https://www.instagram.com/samuel.labagnere/" target="_blank">
        <img alt="Instagram" src={instagram} />
      </a>
      <a href="https://github.com/Samuel-Labagnere/" target="_blank">
        <img alt="Github" src={github} />
      </a>
    </div>
  </section>
</section>