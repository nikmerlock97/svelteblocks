<script lang="ts">
  import CopyToClipboard from "./CopyClipBoard.svelte";

  import { onMount } from "svelte";
  import Clipboard from "./../icons/Clipboard.svelte";
  let _Prism: any;

  type Language =
    | "js"
    | "javascript"
    | "typescript"
    | "svelte"
    | "css"
    | "scss";

  /** Source Code to Display */
  export let code = "let b = 4;";
  /** Language of Source Code */
  export let language: Language = "typescript";
  /** Fix spacing */
  export let normalizeWhiteSpace = true;
  /** Display Number Lines */
  export let showLineNumbers = false;

  export let theme: string = "indigo";

  export let copied = false;

  onMount(async () => {
    // Load the prismjs first after the page is loaded
    const prismModule = await import("svelte-prismjs");
    await import("prismjs/components/prism-javascript.js");
    await import("prismjs/components/prism-typescript.js");
    await import("prismjs/components/prism-graphql.js");
    await import("prismjs/components/prism-css.js");
    await import("prismjs/components/prism-scss.js");
    await import("prism-svelte");

    await import("prismjs/plugins/line-highlight/prism-line-highlight.js");
    await import("prismjs/plugins/file-highlight/prism-file-highlight.js");
    // Once everything is loaded load the prismjs module
    _Prism = prismModule.default;
  });

  function copyToClipboard() {
    // const code = beautifyHTML(markup);
    // var input = document.createElement("textarea");
    // input.innerHTML = code;
    // document.body.appendChild(input);
    // input.select();
    // document.execCommand("copy");
    // document.body.removeChild(input);
    copied = true;
    setTimeout(() => {
      copied = false;
    }, 2000);
  }
</script>

<div class="container relative mx-auto">
  <div class="absolute rounded-full shadow-md cursor-pointer top-4 right-4">
    <CopyToClipboard
      text={code}
      on:copy={({ detail }) => {
        // TODO: Notification Popup displaying "Copied!"
        copyToClipboard();
      }}
      let:copy
    >
      <!-- <span class="text-black" on:click={copy}>COPY</span> -->
      <div class="clipboard-wrapper">
        <button
          class="bg-{theme}-500 copy-the-block copy-to-clipboard"
          on:click={copy}
        >
          <Clipboard />
          <span>COPY TO CLIPBOARD</span>
        </button>
        <span
          class:is-copied={!!copied}
          class="clipboard-tooltip"
        >Copied!</span>
      </div>
    </CopyToClipboard>
  </div>
  <svelte:component
    this={_Prism}
    class="rounded-lg"
    {code}
    {language}
    {normalizeWhiteSpace}
    {showLineNumbers}
  />
</div>
