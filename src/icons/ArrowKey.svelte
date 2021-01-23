<script lang="ts">
  // your script goes here
  export let dir: "up" | "down" | "left" | "right" = "right";
</script>

<!-- markup (zero or more items) goes here -->
{#if dir === 'up'}
  <svg
    stroke="currentColor"
    stroke-width="2"
    fill="none"
    stroke-linecap="round"
    stroke-linejoin="round"
    viewBox="0 0 24 24"
  >
    <path d="M12 19V5M5 12l7-7 7 7" />
  </svg>
{:else if dir === 'down'}
  <svg
    stroke="currentColor"
    stroke-width="2"
    fill="none"
    stroke-linecap="round"
    stroke-linejoin="round"
    viewBox="0 0 24 24"
  >
    <path d="M12 5v14M19 12l-7 7-7-7" />
  </svg>
{:else if dir === 'left'}
  <svg
    stroke="currentColor"
    stroke-width="2"
    fill="none"
    stroke-linecap="round"
    stroke-linejoin="round"
    viewBox="0 0 24 24"
  >
    <path d="M19 12H5M12 19l-7-7 7-7" />
  </svg>
{:else}
  <svg
    stroke="currentColor"
    stroke-width="2"
    fill="none"
    stroke-linecap="round"
    stroke-linejoin="round"
    viewBox="0 0 24 24"
  >
    <path d="M5 12h14M12 5l7 7-7 7" />
  </svg>
{/if}

<style>
  /* your styles go here */
</style>
