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
  };
  Object.entries(iconList).forEach(([type, icons]) => {
    Object.keys(icons).map((name) => blockListArr.push(`${name},${type}`));
  });

  return { blockListArr, iconList };
};
</script>

<script>
import { stores } from "@sapper/app";
import _BlogA from "./../blocks/blog/a.svelte";
import _BlogB from "./../blocks/blog/b.svelte";
import _BlogC from "./../blocks/blog/c.svelte";

export let sidebar = false;
export let iconList;
export let blockListArr = [];

const desktopIcon = () => {
  return `<svg
    stroke="currentColor"
    stroke-width=${2}
    fill="none"
    stroke-linecap="round"
    stroke-linejoin="round"
    viewBox="0 0 24 24"
  >
    <rect x=${2} y=${3} width=${20} height=${14} rx=${2} ry=${2} />
    <path d="M8 21h8m-4-4v4" />
  </svg>`;
};

const phoneIcon = () => {
  return `<svg
    viewBox="0 0 24 24"
    stroke="currentColor"
    stroke-width=${2}
    fill="none"
    stroke-linecap="round"
    stroke-linejoin="round"
  >
    <rect x=${5} y=${2} width=${14} height=${20} rx=${2} ry=${2} />
    <path d="M12 18h.01" />
  </svg>`;
};

const tabletIcon = () => {
  return `<svg
    viewBox="0 0 24 24"
    stroke="currentColor"
    stroke-width=${2}
    fill="none"
    stroke-linecap="round"
    stroke-linejoin="round"
  >
    <rect x=${4} y=${2} width=${16} height=${20} rx=${2} ry=${2} />
    <path d="M12 18h.01" />
  </svg>`;
};

const clipboardIcon = () => {
  return `<svg
    viewBox="0 0 25 24"
    stroke="currentColor"
    stroke-width=${2}
    fill="none"
    stroke-linecap="round"
    stroke-linejoin="round"
  >
    <path d="M19.914 1h-18v19"/>
    <path d="M6 5v18h18V5z"/>
  </svg>`;
};

const viewList = [
  {
    icon: desktopIcon(),
    name: "desktop",
  },
  {
    icon: tabletIcon(),
    name: "tablet",
  },
  {
    icon: phoneIcon(),
    name: "phone",
  },
];

const themeList = [
  "indigo",
  "yellow",
  "red",
  "purple",
  "pink",
  "blue",
  "green",
];
let ready = true;
let darkMode = false;
let copied = false;
let codeView = false;
let currentKeyCode = null;
let view = "desktop";
let theme = "indigo";
let blockType = "Blog";
let blockName = "BlogA";
let markup = "";

function handleMenu(event: any) {
  sidebar = event.detail.value;
}

const getBlock = (theme: string, darkMode: boolean) => {
  return {
    Blog: {
      BlogA: _BlogA,
      BlogB: _BlogB,
      BlogC: _BlogC,
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
  // const { blockType, blockName } = this.state;
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
    if (keyCode === 37 || keyCode === 38 || keyCode === 39 || keyCode === 40) {
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

<svelte:window on:keydown="{keyboardNavigation}" />
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
  class:has-sidebar="{!!sidebar}"
  class:dark-mode="{!!darkMode}"
  class="app {theme} {view}"
>
  <textarea class="copy-textarea"></textarea>
  <aside class="sidebar">
    {#each Object.entries(iconList) as [type, icons]}
      <div class="blocks" let-key="{type}">
        <div class="block-category">{type}</div>
        <div class="block-list">
          {#each Object.entries(icons) as icon}
            <button
              let-key="{icon[0]}"
              tabIndex="0"
              on:click="{() => changeBlock(icon[0], type)}"
              class="block-item"
              class:is-active="{icon[0] === blockName}"
              block-type="{type}"
              block-name="{icon[0]}"
            ><svelte:component this="{icon[1]}" /></button>
          {/each}
        </div>
      </div>
    {/each}
  </aside>
  <div class="toolbar">
    <button
      class="text-lg tracking-widest opener"
      on:click="{toggleSidebar}"
    >SvelteBlocks</button>
    {#if !!codeView}
      <!-- content here -->
      <div class="clipboard-wrapper">
        <button
          class="copy-the-block copy-to-clipboard"
          on:click="{() => copyToClipboard}"
        >
          {@html clipboardIcon()}
          <span>COPY TO CLIPBOARD</span>
        </button>
        <span
          class:is-copied="{!!copied}"
          class="clipboard-tooltip"
        >Copied!</span>
      </div>
    {/if}
    <button class="copy-the-block" on:click="{toggleView}">
      {#if !codeView}
        <svg
          fill="none"
          stroke="currentColor"
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="2"
          viewBox="0 0 24 24"
        >
          <path d="M16 18L22 12 16 6"></path>
          <path d="M8 6L2 12 8 18"></path>
        </svg>
      {:else}
        <svg
          fill="none"
          stroke="currentColor"
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="2"
          class="css-i6dzq1"
          viewBox="0 0 24 24"
        >
          <path d="M1 12s4-8 11-8 11 8 11 8-4 8-11 8-11-8-11-8z"></path>
          <circle cx="12" cy="12" r="3"></circle>
        </svg>
      {/if}
      <span>{!codeView ? 'VIEW CODE' : 'PREVIEW'}</span>
    </button>
    <div class="switcher">
      {#each themeList as t, k}
        <button
          let-key="{k}"
          data-theme="{t}"
          on:keydown="{(event) => keyboardNavigation(event)}"
          class="theme-button bg-{t}-500"
          class:is-active="{theme === t}"
          on:click="{changeTheme}"
        ></button>
      {/each}
    </div>
    {#each viewList as v, k}
      <button
        let-key="{k}"
        class:is-active="{view === v.name}"
        class="device"
        data-view="{v.name}"
        on:click="{(e) => changeView(e)}"
      >
        {@html v.icon}</button>
    {/each}
    <button class="mode" on:click="{changeMode}"></button>
  </div>
  <div class="markup">
    <svelte:component
      this="{getBlock(theme, darkMode)[blockType][blockName]}"
    />
  </div>
  <main class="main" class:opacity-0="{!ready}">
    <div class="view" class:show-code="{!!codeView}">
      <!-- <Frame
        contentDidMount={this.handleContentDidMount}
        contentDidUpdate={this.handleContentDidUpdate}
        head={
          <>
          <link href="https://cdnjs.cloudflare.com/ajax/libs/tailwindcss/2.0.2/tailwind.min.css" rel="stylesheet" />
          {
            <style dangerouslySetInnerHTML={{__html:
              `img { filter:
                ${darkMode ?
                  'invert(1) opacity(.5); mix-blend-mode: luminosity; }'
                  :
                  'sepia(1) hue-rotate(190deg) opacity(.46) grayscale(.7) }'
                }`
              }}
            />
          }
          </>
        }
      >
        {getBlock({ theme, darkMode })[blockType][blockName]}
      </Frame> -->
      <svelte:component
        this="{getBlock(theme, darkMode)[blockType][blockName]}"
        darkMode="{darkMode}"
        theme="{theme}"
      />
      <div class="codes">
        <!-- {beautifyHTML(markup)} -->
        <!-- <SyntaxHighlighter language="html" style={darkMode ? vs2015 : docco} showLineNumbers>
          {this.beautifyHTML(this.state.markup)}
        </SyntaxHighlighter> -->
      </div>
    </div>
  </main>
  <a
    href="https://github.com/nikmerlock97/ubiquitous-memory"
    class="github"
    target="_blank"
    rel="noopener noreferrer"
  >
    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24">
      <path
        fill="currentColor"
        d="M12 .5C5.37.5 0 5.78 0 12.292c0 5.211 3.438 9.63 8.205 11.188.6.111.82-.254.82-.567 0-.28-.01-1.022-.015-2.005-3.338.711-4.042-1.582-4.042-1.582-.546-1.361-1.335-1.725-1.335-1.725-1.087-.731.084-.716.084-.716 1.205.082 1.838 1.215 1.838 1.215 1.07 1.803 2.809 1.282 3.495.981.108-.763.417-1.282.76-1.577-2.665-.295-5.466-1.309-5.466-5.827 0-1.287.465-2.339 1.235-3.164-.135-.298-.54-1.497.105-3.121 0 0 1.005-.316 3.3 1.209.96-.262 1.98-.392 3-.398 1.02.006 2.04.136 3 .398 2.28-1.525 3.285-1.209 3.285-1.209.645 1.624.24 2.823.12 3.121.765.825 1.23 1.877 1.23 3.164 0 4.53-2.805 5.527-5.475 5.817.42.354.81 1.077.81 2.182 0 1.578-.015 2.846-.015 3.229 0 .309.21.678.825.56C20.565 21.917 24 17.495 24 12.292 24 5.78 18.627.5 12 .5z"
      ></path>
    </svg>
    GitHub
  </a>
  <div class="keyboard-nav">
    <div
      class="k-up keyboard-button"
      class:is-active="{currentKeyCode === 38}"
      data-info="Previous block"
    >
      <svg
        stroke="currentColor"
        stroke-width="2"
        fill="none"
        stroke-linecap="round"
        stroke-linejoin="round"
        viewBox="0 0 24 24"
      >
        <path d="M12 19V5M5 12l7-7 7 7"></path>
      </svg>
    </div>
    <div class="keyboard-nav-row">
      <div
        class="k-left keyboard-button"
        class:is-active="{currentKeyCode === 37}"
        data-info="Hide sidebar"
      >
        <svg
          stroke="currentColor"
          stroke-width="2"
          fill="none"
          stroke-linecap="round"
          stroke-linejoin="round"
          viewBox="0 0 24 24"
        >
          <path d="M19 12H5M12 19l-7-7 7-7"></path>
        </svg>
      </div>
      <div
        class="k-down keyboard-button"
        class:is-active="{currentKeyCode === 40}"
        data-info="Next block"
      >
        <svg
          stroke="currentColor"
          stroke-width="2"
          fill="none"
          stroke-linecap="round"
          stroke-linejoin="round"
          viewBox="0 0 24 24"
        >
          <path d="M12 5v14M19 12l-7 7-7-7"></path>
        </svg>
      </div>
      <div
        class="k-right keyboard-button"
        class:is-active="{currentKeyCode === 39}"
        data-info="Show sidebar"
      >
        <svg
          stroke="currentColor"
          stroke-width="2"
          fill="none"
          stroke-linecap="round"
          stroke-linejoin="round"
          viewBox="0 0 24 24"
        >
          <path d="M5 12h14M12 5l7 7-7 7"></path>
        </svg>
      </div>
    </div>
  </div>
</div>
