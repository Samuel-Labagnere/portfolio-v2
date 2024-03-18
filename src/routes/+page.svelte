<script lang="ts">
  import logo from '$lib/assets/logo.png';
  import sam from '$lib/assets/sam.jpg';
  import linkedin from '$lib/assets/linkedin.svg';
  import instagram from '$lib/assets/instagram.svg';
  import github from '$lib/assets/github.svg';
  import global from "$lib/json/global.json";
</script>

<section class="relative h-screen overflow-hidden">
  <header class="flex flex-col items-center">
    <img alt="Logo de Samuel Labagnere" src={logo} class="w-20" />
    <div class="flex flex-col items-center uppercase">
      <h1 class="text-2xl">Samuel Labagnere</h1>
      <h2 class="text-lg">{global.title}</h2>
    </div>
  </header>
  
  <section class="md:relative">
    <div class="absolute flex flex-col mt-5 md:mt-0 md:justify-center items-center gap-2.5 w-full h-full">
      <div class="flex flex-col justify-center gap-2.5 md:gap-64 md:flex-row md:justify-between items-center">
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
      </div>  

      <a href="/about" class="btn !bg-primary/75 !text-black">
        À propos
      </a>
    </div>

    <img alt="Samuel Labagnere en costume" src={sam} class="mx-auto" />

  </section>
  <div class="hidden absolute bottom-0 md:flex justify-center items-center w-full md:my-5 gap-6">
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