<script context="module">
  export const preload = () => {};
</script>

<script>
  import { fade } from "svelte/transition";

  let controlsLayout = [
    "previousFrame",
    "playpause",
    "stop",
    "nextFrame",
    "progress",
    "frame",
    "loop",
    "spacer",
    "background",
    "snapshot",
    "zoom",
    "info",
  ];

  let lottie = `./heroLottieAlt.json`;
</script>

<svelte:head>
  <!--<script
    src="https://unpkg.com/@lottiefiles/lottie-player@latest/dist/lottie-player.js" ✂prettier:content✂="CiAg">{}</script>-->
  <title>SvelteBlocks - ready-to-go Svelte code blocks</title>
</svelte:head>
<main in:fade={{ duration: 500 }}>
  <!-- component -->
  <section class="text-gray-700 bg-white body-font">
    <div
      class="container flex flex-col items-center px-5 pt-6 pb-12 mx-auto md:py-24 md:flex-row"
    >
      <div class="w-5/6 lg:max-w-lg lg:w-full md:w-1/2" />
    </div>
  </section>
</main>
