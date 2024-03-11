<svelte:head>
  { head ?? '' }
  <link bind:this="{darkThemeIcon}" rel="icon" id="darkThemeIcon" type="image/png" href="assets/Icon-dark.png" />
  <link bind:this="{lightThemeIcon}" rel="icon" id="lightThemeIcon" type="image/png" href="assets/Icon-light.png" />
</svelte:head>

<slot></slot>

<script lang="ts">
  import "../app.css";
  import { onMount } from "svelte";
  
  let lightThemeIcon:HTMLElement;
  let darkThemeIcon:HTMLElement;
  let head:HTMLElement;

  onMount(async () => {
    let matcher = window.matchMedia('(prefers-color-scheme: dark)');
    matcher.addEventListener('change', ThemeChange);
    ThemeChange();

    async function ThemeChange() {
      if (matcher.matches) {
        lightThemeIcon?.remove();
        document.head.append(darkThemeIcon!);
        head = darkThemeIcon;
      } else {
        document.head.append(lightThemeIcon!);
        head = lightThemeIcon;
      }
    }
  });
</script>

<style>
  :global(body){
    background: black;
    color: white;
  }
</style>