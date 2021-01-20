<script>
export let status: number;
export let error: Error;

const mode = process.env.NODE_ENV;
const dev = mode === "development";
</script>

<section class="flex flex-col items-center justify-center flex-1">
  <h1 class="text-2xl text-red-700">{error.message}</h1>
  <h2 class="mt-1 text-lg text-red-700">{status}</h2>
</section>

{#if dev && error.stack}
  <pre>{error.stack}</pre>
{/if}
