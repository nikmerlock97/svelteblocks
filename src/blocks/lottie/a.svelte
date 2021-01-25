<script lang="ts">
  export let theme: string = "indigo";
  export let darkMode: boolean = false;
</script>

<svelte:head>
  {#if typeof window !== 'undefined'}
    <script
      src="https://unpkg.com/@lottiefiles/lottie-player@latest/dist/lottie-player.js">
    </script>
  {/if}
</svelte:head>
<section class="text-gray-400 body-font">
  <div class="container flex justify-center px-5 py-24 mx-auto">
    <div
      class="w-5/6 bg-white h-52 sm:h-auto md:max-w-lg xl:max-w-2xl lg:w-full md:w-1/2"
    >
      {#if typeof window !== 'undefined'}
        <lottie-player
          src="https://assets6.lottiefiles.com/packages/lf20_slm9nugw.json"
          background="transparent"
          speed="1"
          style="width: 100%; height: 100%;"
          loop={true}
          autoplay={true}
        />
      {/if}
    </div>
  </div>
</section>
