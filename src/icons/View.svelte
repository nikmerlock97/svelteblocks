<script>
// your script goes here
export let screen: "desktop" | "tablet" | "phone" | string = "desktop";

// const desktopIcon = () => {
//   return `<svg
//     stroke="currentColor"
//     stroke-width=${2}
//     fill="none"
//     stroke-linecap="round"
//     stroke-linejoin="round"
//     viewBox="0 0 24 24"
//   >
//     <rect x=${2} y=${3} width=${20} height=${14} rx=${2} ry=${2} />
//     <path d="M8 21h8m-4-4v4" />
//   </svg>`;
// };

// const phoneIcon = () => {
//   return `<svg
//     viewBox="0 0 24 24"
//     stroke="currentColor"
//     stroke-width=${2}
//     fill="none"
//     stroke-linecap="round"
//     stroke-linejoin="round"
//   >
//     <rect x=${5} y=${2} width=${14} height=${20} rx=${2} ry=${2} />
//     <path d="M12 18h.01" />
//   </svg>`;
// };

// const tabletIcon = () => {
//   return `<svg
//     viewBox="0 0 24 24"
//     stroke="currentColor"
//     stroke-width=${2}
//     fill="none"
//     stroke-linecap="round"
//     stroke-linejoin="round"
//   >
//     <rect x=${4} y=${2} width=${16} height=${20} rx=${2} ry=${2} />
//     <path d="M12 18h.01" />
//   </svg>`;
// };
</script>

<style>
/* your styles go here */
</style>

<!-- markup (zero or more items) goes here -->
{#if screen === 'tablet'}
  <svg
    viewBox="0 0 24 24"
    stroke="currentColor"
    stroke-width="{2}"
    fill="none"
    stroke-linecap="round"
    stroke-linejoin="round"
  >
    <rect x="{4}" y="{2}" width="{16}" height="{20}" rx="{2}" ry="{2}"></rect>
    <path d="M12 18h.01"></path>
  </svg>
{:else if screen === 'phone'}
  <svg
    viewBox="0 0 24 24"
    stroke="currentColor"
    stroke-width="{2}"
    fill="none"
    stroke-linecap="round"
    stroke-linejoin="round"
  >
    <rect x="{5}" y="{2}" width="{14}" height="{20}" rx="{2}" ry="{2}"></rect>
    <path d="M12 18h.01"></path>
  </svg>
{:else}
  <svg
    stroke="currentColor"
    stroke-width="{2}"
    fill="none"
    stroke-linecap="round"
    stroke-linejoin="round"
    viewBox="0 0 24 24"
  >
    <rect x="{2}" y="{3}" width="{20}" height="{14}" rx="{2}" ry="{2}"></rect>
    <path d="M8 21h8m-4-4v4"></path>
  </svg>
{/if}
