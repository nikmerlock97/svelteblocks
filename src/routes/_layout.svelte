<script context="module">
  import blogA from "./../icons/blog/a.svelte";
  import blogB from "./../icons/blog/b.svelte";
  import blogC from "./../icons/blog/c.svelte";
  export const preload = () => {
    const blockListArr = [];
    const iconList = {
      Blog: {
        BlogA: blogA,
        BlogB: blogB,
        BlogC: blogC,
      },
      Lottie: {
        LottieA: blogA,
      },
    };
    Object.entries(iconList).forEach(([type, icons]) => {
      Object.keys(icons).map((name) => blockListArr.push(`${name},${type}`));
    });

    return { blockListArr, iconList };
  };
</script>

<script lang="ts">
  import { stores } from "@sapper/app";
  import { fade } from "svelte/transition";
  import Prism from "./../components/Prism.svelte";

  const code_sample = `
<script lang="ts">
  let count: number = 0;
</script\>

\<button on:click={ () => count++ }\>Hello</button\>

\<h1\>{ count }</h1\>

<ul\>
  {#each Array(10).map((_, i) => i) as }
    <li on:click={() => count = i}>Set count to {i}</li>
  {/each}
</ul\>
` as string;
  // Icons
  import ArrowKey from "./../icons/ArrowKey.svelte";
  import Code from "./../icons/Code.svelte";
  import Preview from "./../icons/Preview.svelte";
  import View from "./../icons/View.svelte";
  import Clipboard from "./../icons/Clipboard.svelte";
  import GitHub from "./../icons/GitHub.svelte";

  // Components/Blocks
  import _BlogA from "./../blocks/blog/a.svelte";
  import _BlogB from "./../blocks/blog/b.svelte";
  import _BlogC from "./../blocks/blog/c.svelte";
  import _LottieA from "./../blocks/lottie/a.svelte";

  export let iconList;
  export let blockListArr = [];

  // Enums
  const viewList = ["desktop", "tablet", "phone"];
  const themeList = [
    "indigo",
    "yellow",
    "red",
    "purple",
    "pink",
    "blue",
    "green",
  ];

  //TODO: Place below props in store
  let ready = true;
  let darkMode = false;
  let copied = false;
  let codeView = false;
  let currentKeyCode = null;
  let view: "desktop" | "tablet" | "phone" = "desktop";
  let theme = "indigo";
  let blockType = "Blog";
  let blockName = "BlogA";
  let markup = "";
  let sidebar: boolean = false;

  const getBlock = (theme: string, darkMode: boolean) => {
    return {
      Blog: {
        BlogA: _BlogA,
        BlogB: _BlogB,
        BlogC: _BlogC,
      },
      Lottie: {
        LottieA: _LottieA,
      },
    };
  };

  const changeBlock = (_blockName, _blockType) => {
    codeView = false;
    blockType = _blockType;
    blockName = _blockName;
  };

  function changeTheme(e) {
    const { currentTarget } = e;
    const _theme = currentTarget.getAttribute("data-theme");
    theme = _theme;
  }

  function changeView(e) {
    const { currentTarget } = e;
    const _view = currentTarget.getAttribute("data-view");
    view = _view;
    codeView = false;
  }

  function keyboardNavigation(e) {
    const blockStringFormat = `${blockName},${blockType}`;
    const keyCode = e.which || e.keyCode;

    switch (keyCode) {
      case 40: // Down
        e.preventDefault();
        blockListArr.forEach((block, index) => {
          if (block === blockStringFormat) {
            const newActiveBlock =
              index + 1 <= blockListArr.length - 1
                ? blockListArr[index + 1].split(",")
                : blockListArr[0].split(",");
            const newBlockName = newActiveBlock[0];
            const newBlockType = newActiveBlock[1];
            const newBlockNode = document.querySelector(
              `.block-item[block-name="${newBlockName}"]`
            );
            if (newBlockNode)
              // newBlockNode.focus();
              blockType = newBlockType;
            blockName = newBlockName;
            codeView = false;
            currentKeyCode = 40;
          }
        });
        break;
      case 37: // Left
        e.preventDefault();
        sidebar = false;
        currentKeyCode = 37;
        break;
      case 39: // Right
        e.preventDefault();
        sidebar = true;
        currentKeyCode = 39;
        break;
      case 38: // Up
        e.preventDefault();
        blockListArr.forEach((block, index) => {
          if (block === blockStringFormat) {
            const newActiveBlock =
              index - 1 >= 0
                ? blockListArr[index - 1].split(",")
                : blockListArr[blockListArr.length - 1].split(",");
            const newBlockName = newActiveBlock[0];
            const newBlockType = newActiveBlock[1];
            const newBlockNode = document.querySelector(
              `.block-item[block-name="${newBlockName}"]`
            );
            if (newBlockNode)
              // newBlockNode.focus();
              blockName = newBlockName;
            blockType = newBlockType;
            codeView = false;
            currentKeyCode = 38;
          }
        });
        break;
      default:
        return;
    }

    setTimeout(() => {
      if (
        keyCode === 37 ||
        keyCode === 38 ||
        keyCode === 39 ||
        keyCode === 40
      ) {
        currentKeyCode = null;
      }
    }, 200);
  }

  function beautifyHTML(codeStr) {
    const process = (str) => {
      let div = document.createElement("div");
      div.innerHTML = str.trim();
      return format(div, 0).innerHTML.trim();
    };

    const format = (node, level) => {
      let indentBefore = new Array(level++ + 1).join("  "),
        indentAfter = new Array(level - 1).join("  "),
        textNode;

      for (let i = 0; i < node.children.length; i++) {
        textNode = document.createTextNode("\n" + indentBefore);
        node.insertBefore(textNode, node.children[i]);

        format(node.children[i], level);

        if (node.lastElementChild === node.children[i]) {
          textNode = document.createTextNode("\n" + indentAfter);
          node.appendChild(textNode);
        }
      }

      return node;
    };
    return process(codeStr);
  }

  function copyToClipboard() {
    const code = beautifyHTML(markup);
    var input = document.createElement("textarea");
    input.innerHTML = code;
    document.body.appendChild(input);
    input.select();
    document.execCommand("copy");
    document.body.removeChild(input);
    copied = true;
    setTimeout(() => {
      copied = false;
    }, 2000);
  }

  const toggleView = () => {
    codeView = !codeView;
    view = "desktop";
    markup = "";
    // this.setState({ codeView: !this.state.codeView, view: 'desktop', markup: this.markupRef.current.innerHTML })
  };

  const toggleSidebar = () => {
    sidebar = !sidebar;
  };

  const changeMode = () => {
    darkMode = !darkMode;
  };

  // You may not want to use `segment`, but it is passed for the time being and will
  // create a warning if not expected: https://github.com/sveltejs/sapper-template/issues/210
  // https://github.com/sveltejs/sapper/issues/824
  export let segment: string = "";
  // Silence unused export property warning
  if (segment) {
  }

  const { page } = stores();

  let current: string;
  $: current = $page.path;
</script>

<style>
  .view.dark :global(img) {
    filter: invert(1) opacity(0.5);
    mix-blend-mode: luminosity;
  }

  .view.light > :global(img) {
    filter: sepia(1) hue-rotate(190deg) opacity(0.46) grayscale(0.7);
  }
</style>

<svelte:window on:keydown={keyboardNavigation} />
<svelte:head>
  {#if sidebar}
    <style>
      body {
        overflow: hidden;
      }
    </style>
  {/if}
</svelte:head>
<div
  class:has-sidebar={!!sidebar}
  class:dark-mode={!!darkMode}
  class="app {theme} {view}"
>
  <textarea class="copy-textarea" />
  <aside class="sidebar">
    {#each Object.entries(iconList) as [type, icons]}
      <div class="blocks" let-key={type}>
        <div class="block-category">{type}</div>
        <div class="block-list">
          {#each Object.entries(icons) as icon}
            <button
              let-key={icon[0]}
              tabIndex="0"
              on:click={() => changeBlock(icon[0], type)}
              class="block-item"
              class:is-active={icon[0] === blockName}
              block-type={type}
              block-name={icon[0]}
            ><svelte:component this={icon[1]} /></button>
          {/each}
        </div>
      </div>
    {/each}
  </aside>
  <div class="toolbar">
    <button
      class="text-lg tracking-widest opener"
      on:click={toggleSidebar}
    >SvelteBlocks</button>
    <!-- {#if !!codeView}
      <div class="clipboard-wrapper">
        <button
          class="copy-the-block copy-to-clipboard"
          on:click={() => copyToClipboard}
        >
          <Clipboard />
          <span>COPY TO CLIPBOARD</span>
        </button>
        <span
          class:is-copied={!!copied}
          class="clipboard-tooltip"
        >Copied!</span>
      </div>
    {/if} -->
    <button class="copy-the-block" on:click={toggleView}>
      {#if !codeView}
        <Code />
      {:else}
        <Preview />
      {/if}
      <span>{!codeView ? 'VIEW CODE' : 'PREVIEW'}</span>
    </button>
    <div class="switcher">
      {#each themeList as t, k}
        <button
          let-key={k}
          data-theme={t}
          on:keydown={(event) => keyboardNavigation(event)}
          class="theme-button bg-{t}-500"
          class:is-active={theme === t}
          on:click={changeTheme}
        />
      {/each}
    </div>
    {#each viewList as v, k}
      <button
        let-key={k}
        class:is-active={view === v}
        class="device"
        data-view={v}
        on:click={(e) => changeView(e)}
      >
        <View screen={v} />
      </button>
    {/each}
    <button class="mode" on:click={changeMode} />
  </div>
  <div class="markup">
    <svelte:component this={getBlock(theme, darkMode)[blockType][blockName]} />
  </div>
  <main class="main" class:opacity-0={!ready}>
    <div
      class="view"
      class:dark={!!darkMode}
      class:light={!darkMode}
      class:show-code={!!codeView}
    >
      <!-- TODO: This is how it rendered the code with IFRAME -->
      {#if !codeView}
        <svelte:component
          this={getBlock(theme, darkMode)[blockType][blockName]}
          {darkMode}
          {theme}
        />
      {/if}
      {#if !!codeView}
        <div transition:fade={{ delay: 0, duration: 250 }} class="codes">
          <Prism
            showLineNumbers={true}
            bind:theme
            code={code_sample}
            language="svelte"
          />
        </div>
      {/if}
    </div>
  </main>
  <!-- TODO: Turn below into a component -->
  <a
    href="https://github.com/nikmerlock97/svelteblocks"
    class="github"
    target="_blank"
    rel="noopener noreferrer"
  >
    <GitHub />
    GitHub
  </a>
  <!-- TODO: Turn below into a component -->
  <div class="keyboard-nav">
    <div
      class="k-up keyboard-button"
      class:is-active={currentKeyCode === 38}
      data-info="Previous block"
    >
      <ArrowKey dir={'up'} />
    </div>
    <div class="keyboard-nav-row">
      <div
        class="k-left keyboard-button"
        class:is-active={currentKeyCode === 37}
        data-info="Hide sidebar"
      >
        <ArrowKey dir={'left'} />
      </div>
      <div
        class="k-down keyboard-button"
        class:is-active={currentKeyCode === 40}
        data-info="Next block"
      >
        <ArrowKey dir={'down'} />
      </div>
      <div
        class="k-right keyboard-button"
        class:is-active={currentKeyCode === 39}
        data-info="Show sidebar"
      >
        <ArrowKey dir={'right'} />
      </div>
    </div>
  </div>
</div>
