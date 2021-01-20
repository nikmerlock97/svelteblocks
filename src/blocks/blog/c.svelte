<script lang="ts">
export let theme: string = "indigo";
export let darkMode: boolean = false;
</script>

{#if !darkMode}
  <section class="overflow-hidden text-gray-600 body-font">
    <div class="container px-5 py-24 mx-auto">
      <div class="flex flex-wrap -m-12">
        <div class="flex flex-col items-start p-12 md:w-1/2">
          <span
            class="{`inline-block py-1 px-2 rounded bg-${theme}-50 text-${theme}-500 text-xs font-medium tracking-widest`}"
          >
            CATEGORY
          </span>
          <h2
            class="mt-4 mb-4 text-2xl font-medium text-gray-900 sm:text-3xl title-font"
          >
            Roof party normcore before they sold out, cornhole vape
          </h2>
          <p class="mb-8 leading-relaxed">
            Live-edge letterpress cliche, salvia fanny pack humblebrag narwhal
            portland. VHS man braid palo santo hoodie brunch trust fund. Bitters
            hashtag waistcoat fashion axe chia unicorn. Plaid fixie chambray
            90's, slow-carb etsy tumeric. Cray pug you probably haven't heard of
            them hexagon kickstarter craft beer pork chic.
          </p>
          <div
            class="flex flex-wrap items-center w-full pb-4 mt-auto mb-4 border-b-2 border-gray-100"
          >
            <a href="/" class="{`text-${theme}-500 inline-flex items-center`}">
              Learn More
              <svg
                class="w-4 h-4 ml-2"
                viewBox="0 0 24 24"
                stroke="currentColor"
                stroke-width="{2}"
                fill="none"
                stroke-linecap="round"
                stroke-linejoin="round"
              >
                <path d="M5 12h14"></path>
                <path d="M12 5l7 7-7 7"></path>
              </svg>
            </a>
            <span
              class="inline-flex items-center py-1 pr-3 ml-auto mr-3 text-sm leading-none text-gray-400 border-r-2 border-gray-200"
            >
              <svg
                class="w-4 h-4 mr-1"
                stroke="currentColor"
                stroke-width="{2}"
                fill="none"
                stroke-linecap="round"
                stroke-linejoin="round"
                viewBox="0 0 24 24"
              >
                <path d="M1 12s4-8 11-8 11 8 11 8-4 8-11 8-11-8-11-8z"></path>
                <circle cx="{12}" cy="{12}" r="{3}"></circle>
              </svg>
              1.2K
            </span>
            <span
              class="inline-flex items-center text-sm leading-none text-gray-400"
            >
              <svg
                class="w-4 h-4 mr-1"
                stroke="currentColor"
                stroke-width="{2}"
                fill="none"
                stroke-linecap="round"
                stroke-linejoin="round"
                viewBox="0 0 24 24"
              >
                <path
                  d="M21 11.5a8.38 8.38 0 01-.9 3.8 8.5 8.5 0 01-7.6 4.7 8.38 8.38 0 01-3.8-.9L3 21l1.9-5.7a8.38 8.38 0 01-.9-3.8 8.5 8.5 0 014.7-7.6 8.38 8.38 0 013.8-.9h.5a8.48 8.48 0 018 8v.5z"
                ></path>
              </svg>
              6
            </span>
          </div>
          <a href="/" class="inline-flex items-center">
            <img
              alt="blog"
              src="https://dummyimage.com/104x104"
              class="flex-shrink-0 object-cover object-center w-12 h-12 rounded-full"
            />
            <span class="flex flex-col flex-grow pl-4">
              <span class="font-medium text-gray-900 title-font">
                Holden Caulfield
              </span>
              <span class="text-gray-400 text-xs tracking-widest mt-0.5">UI
                DEVELOPER</span>
            </span>
          </a>
        </div>
        <div class="flex flex-col items-start p-12 md:w-1/2">
          <span
            class="{`inline-block py-1 px-2 rounded bg-${theme}-50 text-${theme}-500 text-xs font-medium tracking-widest`}"
          >
            CATEGORY
          </span>
          <h2
            class="mt-4 mb-4 text-2xl font-medium text-gray-900 sm:text-3xl title-font"
          >
            Pinterest DIY dreamcatcher gentrify single-origin coffee
          </h2>
          <p class="mb-8 leading-relaxed">
            Live-edge letterpress cliche, salvia fanny pack humblebrag narwhal
            portland. VHS man braid palo santo hoodie brunch trust fund. Bitters
            hashtag waistcoat fashion axe chia unicorn. Plaid fixie chambray
            90's, slow-carb etsy tumeric.
          </p>
          <div
            class="flex flex-wrap items-center w-full pb-4 mt-auto mb-4 border-b-2 border-gray-100"
          >
            <a href="/" class="{`text-${theme}-500 inline-flex items-center`}">
              Learn More
              <svg
                class="w-4 h-4 ml-2"
                viewBox="0 0 24 24"
                stroke="currentColor"
                stroke-width="{2}"
                fill="none"
                stroke-linecap="round"
                stroke-linejoin="round"
              >
                <path d="M5 12h14"></path>
                <path d="M12 5l7 7-7 7"></path>
              </svg>
            </a>
            <span
              class="inline-flex items-center py-1 pr-3 ml-auto mr-3 text-sm leading-none text-gray-400 border-r-2 border-gray-200"
            >
              <svg
                class="w-4 h-4 mr-1"
                stroke="currentColor"
                stroke-width="{2}"
                fill="none"
                stroke-linecap="round"
                stroke-linejoin="round"
                viewBox="0 0 24 24"
              >
                <path d="M1 12s4-8 11-8 11 8 11 8-4 8-11 8-11-8-11-8z"></path>
                <circle cx="{12}" cy="{12}" r="{3}"></circle>
              </svg>
              1.2K
            </span>
            <span
              class="inline-flex items-center text-sm leading-none text-gray-400"
            >
              <svg
                class="w-4 h-4 mr-1"
                stroke="currentColor"
                stroke-width="{2}"
                fill="none"
                stroke-linecap="round"
                stroke-linejoin="round"
                viewBox="0 0 24 24"
              >
                <path
                  d="M21 11.5a8.38 8.38 0 01-.9 3.8 8.5 8.5 0 01-7.6 4.7 8.38 8.38 0 01-3.8-.9L3 21l1.9-5.7a8.38 8.38 0 01-.9-3.8 8.5 8.5 0 014.7-7.6 8.38 8.38 0 013.8-.9h.5a8.48 8.48 0 018 8v.5z"
                ></path>
              </svg>
              6
            </span>
          </div>
          <a href="/" class="inline-flex items-center">
            <img
              alt="blog"
              src="https://dummyimage.com/103x103"
              class="flex-shrink-0 object-cover object-center w-12 h-12 rounded-full"
            />
            <span class="flex flex-col flex-grow pl-4">
              <span class="font-medium text-gray-900 title-font">
                Alper Kamu
              </span>
              <span
                class="text-gray-400 text-xs tracking-widest mt-0.5"
              >DESIGNER</span>
            </span>
          </a>
        </div>
      </div>
    </div>
  </section>
{:else}
  <section class="overflow-hidden text-gray-400 bg-gray-900 body-font">
    <div class="container px-5 py-24 mx-auto">
      <div class="flex flex-wrap -m-12">
        <div class="flex flex-col items-start p-12 md:w-1/2">
          <span
            class="inline-block px-2 py-1 text-xs font-medium tracking-widest text-gray-400 text-opacity-75 bg-gray-800 rounded"
          >
            CATEGORY
          </span>
          <h2
            class="mt-4 mb-4 text-2xl font-medium text-white sm:text-3xl title-font"
          >
            Roof party normcore before they sold out, cornhole vape
          </h2>
          <p class="mb-8 leading-relaxed">
            Live-edge letterpress cliche, salvia fanny pack humblebrag narwhal
            portland. VHS man braid palo santo hoodie brunch trust fund. Bitters
            hashtag waistcoat fashion axe chia unicorn. Plaid fixie chambray
            90's, slow-carb etsy tumeric. Cray pug you probably haven't heard of
            them hexagon kickstarter craft beer pork chic.
          </p>
          <div
            class="flex flex-wrap items-center w-full pb-4 mt-auto mb-4 border-b-2 border-gray-800 border-opacity-75"
          >
            <a href="/" class="{`text-${theme}-400 inline-flex items-center`}">
              Learn More
              <svg
                class="w-4 h-4 ml-2"
                viewBox="0 0 24 24"
                stroke="currentColor"
                stroke-width="{2}"
                fill="none"
                stroke-linecap="round"
                stroke-linejoin="round"
              >
                <path d="M5 12h14"></path>
                <path d="M12 5l7 7-7 7"></path>
              </svg>
            </a>
            <span
              class="inline-flex items-center py-1 pr-3 ml-auto mr-3 text-sm leading-none text-gray-500 border-r-2 border-gray-800"
            >
              <svg
                class="w-4 h-4 mr-1"
                stroke="currentColor"
                stroke-width="{2}"
                fill="none"
                stroke-linecap="round"
                stroke-linejoin="round"
                viewBox="0 0 24 24"
              >
                <path d="M1 12s4-8 11-8 11 8 11 8-4 8-11 8-11-8-11-8z"></path>
                <circle cx="{12}" cy="{12}" r="{3}"></circle>
              </svg>
              1.2K
            </span>
            <span
              class="inline-flex items-center text-sm leading-none text-gray-500"
            >
              <svg
                class="w-4 h-4 mr-1"
                stroke="currentColor"
                stroke-width="{2}"
                fill="none"
                stroke-linecap="round"
                stroke-linejoin="round"
                viewBox="0 0 24 24"
              >
                <path
                  d="M21 11.5a8.38 8.38 0 01-.9 3.8 8.5 8.5 0 01-7.6 4.7 8.38 8.38 0 01-3.8-.9L3 21l1.9-5.7a8.38 8.38 0 01-.9-3.8 8.5 8.5 0 014.7-7.6 8.38 8.38 0 013.8-.9h.5a8.48 8.48 0 018 8v.5z"
                ></path>
              </svg>
              6
            </span>
          </div>
          <a href="/" class="inline-flex items-center">
            <img
              alt="blog"
              src="https://dummyimage.com/104x104"
              class="flex-shrink-0 object-cover object-center w-12 h-12 rounded-full"
            />
            <span class="flex flex-col flex-grow pl-4">
              <span class="font-medium text-white title-font">
                Holden Caulfield
              </span>
              <span class="text-gray-500 text-xs tracking-widest mt-0.5">UI
                DEVELOPER</span>
            </span>
          </a>
        </div>
        <div class="flex flex-col items-start p-12 md:w-1/2">
          <span
            class="inline-block px-2 py-1 text-xs font-medium tracking-widest text-gray-400 text-opacity-75 bg-gray-800 rounded"
          >
            CATEGORY
          </span>
          <h2
            class="mt-4 mb-4 text-2xl font-medium text-white sm:text-3xl title-font"
          >
            Pinterest DIY dreamcatcher gentrify single-origin coffee
          </h2>
          <p class="mb-8 leading-relaxed">
            Live-edge letterpress cliche, salvia fanny pack humblebrag narwhal
            portland. VHS man braid palo santo hoodie brunch trust fund. Bitters
            hashtag waistcoat fashion axe chia unicorn. Plaid fixie chambray
            90's, slow-carb etsy tumeric.
          </p>
          <div
            class="flex flex-wrap items-center w-full pb-4 mt-auto mb-4 border-b-2 border-gray-800 border-opacity-75"
          >
            <a href="/" class="{`text-${theme}-400 inline-flex items-center`}">
              Learn More
              <svg
                class="w-4 h-4 ml-2"
                viewBox="0 0 24 24"
                stroke="currentColor"
                stroke-width="{2}"
                fill="none"
                stroke-linecap="round"
                stroke-linejoin="round"
              >
                <path d="M5 12h14"></path>
                <path d="M12 5l7 7-7 7"></path>
              </svg>
            </a>
            <span
              class="inline-flex items-center py-1 pr-3 ml-auto mr-3 text-sm leading-none text-gray-500 border-r-2 border-gray-800"
            >
              <svg
                class="w-4 h-4 mr-1"
                stroke="currentColor"
                stroke-width="{2}"
                fill="none"
                stroke-linecap="round"
                stroke-linejoin="round"
                viewBox="0 0 24 24"
              >
                <path d="M1 12s4-8 11-8 11 8 11 8-4 8-11 8-11-8-11-8z"></path>
                <circle cx="{12}" cy="{12}" r="{3}"></circle>
              </svg>
              1.2K
            </span>
            <span
              class="inline-flex items-center text-sm leading-none text-gray-500"
            >
              <svg
                class="w-4 h-4 mr-1"
                stroke="currentColor"
                stroke-width="{2}"
                fill="none"
                stroke-linecap="round"
                stroke-linejoin="round"
                viewBox="0 0 24 24"
              >
                <path
                  d="M21 11.5a8.38 8.38 0 01-.9 3.8 8.5 8.5 0 01-7.6 4.7 8.38 8.38 0 01-3.8-.9L3 21l1.9-5.7a8.38 8.38 0 01-.9-3.8 8.5 8.5 0 014.7-7.6 8.38 8.38 0 013.8-.9h.5a8.48 8.48 0 018 8v.5z"
                ></path>
              </svg>
              6
            </span>
          </div>
          <a href="/" class="inline-flex items-center">
            <img
              alt="blog"
              src="https://dummyimage.com/103x103"
              class="flex-shrink-0 object-cover object-center w-12 h-12 rounded-full"
            />
            <span class="flex flex-col flex-grow pl-4">
              <span class="font-medium text-white title-font">
                Alper Kamu
              </span>
              <span
                class="text-gray-500 text-xs tracking-widest mt-0.5"
              >DESIGNER</span>
            </span>
          </a>
        </div>
      </div>
    </div>
  </section>
{/if}
