<script lang="ts">
export let theme: string = "indigo";
export let darkMode: boolean = false;
</script>

{#if !darkMode}
  <section class="text-gray-600 body-font">
    <div class="container px-5 py-24 mx-auto">
      <div class="flex flex-wrap -m-4">
        <div class="p-4 lg:w-1/3">
          <div
            class="relative h-full px-8 pt-16 pb-24 overflow-hidden text-center bg-gray-100 bg-opacity-75 rounded-lg"
          >
            <h2
              class="mb-1 text-xs font-medium tracking-widest text-gray-400 title-font"
            >
              CATEGORY
            </h2>
            <h1
              class="mb-3 text-xl font-medium text-gray-900 title-font sm:text-2xl"
            >
              Raclette Blueberry Nextious Level
            </h1>
            <p class="mb-3 leading-relaxed">
              Photo booth fam kinfolk cold-pressed sriracha leggings jianbing
              microdosing tousled waistcoat.
            </p>
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
            <div
              class="absolute bottom-0 left-0 flex justify-center w-full py-4 mt-2 leading-none text-center"
            >
              <span
                class="inline-flex items-center py-1 pr-3 mr-3 text-sm leading-none text-gray-400 border-r-2 border-gray-200"
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
          </div>
        </div>
        <div class="p-4 lg:w-1/3">
          <div
            class="relative h-full px-8 pt-16 pb-24 overflow-hidden text-center bg-gray-100 bg-opacity-75 rounded-lg"
          >
            <h2
              class="mb-1 text-xs font-medium tracking-widest text-gray-400 title-font"
            >
              CATEGORY
            </h2>
            <h1
              class="mb-3 text-xl font-medium text-gray-900 title-font sm:text-2xl"
            >
              Ennui Snackwave Thundercats
            </h1>
            <p class="mb-3 leading-relaxed">
              Photo booth fam kinfolk cold-pressed sriracha leggings jianbing
              microdosing tousled waistcoat.
            </p>
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
            <div
              class="absolute bottom-0 left-0 flex justify-center w-full py-4 mt-2 leading-none text-center"
            >
              <span
                class="inline-flex items-center py-1 pr-3 mr-3 text-sm leading-none text-gray-400 border-r-2 border-gray-200"
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
          </div>
        </div>
        <div class="p-4 lg:w-1/3">
          <div
            class="relative h-full px-8 pt-16 pb-24 overflow-hidden text-center bg-gray-100 bg-opacity-75 rounded-lg"
          >
            <h2
              class="mb-1 text-xs font-medium tracking-widest text-gray-400 title-font"
            >
              CATEGORY
            </h2>
            <h1
              class="mb-3 text-xl font-medium text-gray-900 title-font sm:text-2xl"
            >
              Selvage Poke Waistcoat Godard
            </h1>
            <p class="mb-3 leading-relaxed">
              Photo booth fam kinfolk cold-pressed sriracha leggings jianbing
              microdosing tousled waistcoat.
            </p>
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
            <div
              class="absolute bottom-0 left-0 flex justify-center w-full py-4 mt-2 leading-none text-center"
            >
              <span
                class="inline-flex items-center py-1 pr-3 mr-3 text-sm leading-none text-gray-400 border-r-2 border-gray-200"
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
          </div>
        </div>
      </div>
    </div>
  </section>
{:else}
  <section class="text-gray-400 bg-gray-900 body-font">
    <div class="container px-5 py-24 mx-auto">
      <div class="flex flex-wrap -m-4">
        <div class="p-4 lg:w-1/3">
          <div
            class="relative h-full px-8 pt-16 pb-24 overflow-hidden text-center bg-gray-800 rounded-lg bg-opacity-40"
          >
            <h2
              class="mb-1 text-xs font-medium tracking-widest text-gray-500 title-font"
            >
              CATEGORY
            </h2>
            <h1
              class="mb-3 text-xl font-medium text-white title-font sm:text-2xl"
            >
              Raclette Blueberry Nextious Level
            </h1>
            <p class="mb-3 leading-relaxed">
              Photo booth fam kinfolk cold-pressed sriracha leggings jianbing
              microdosing tousled waistcoat.
            </p>
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
            <div
              class="absolute bottom-0 left-0 flex justify-center w-full py-4 mt-2 leading-none text-center"
            >
              <span
                class="inline-flex items-center py-1 pr-3 mr-3 text-sm leading-none text-gray-500 border-r-2 border-gray-700 border-opacity-50"
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
          </div>
        </div>
        <div class="p-4 lg:w-1/3">
          <div
            class="relative h-full px-8 pt-16 pb-24 overflow-hidden text-center bg-gray-800 rounded-lg bg-opacity-40"
          >
            <h2
              class="mb-1 text-xs font-medium tracking-widest text-gray-500 title-font"
            >
              CATEGORY
            </h2>
            <h1
              class="mb-3 text-xl font-medium text-white title-font sm:text-2xl"
            >
              Ennui Snackwave Thundercats
            </h1>
            <p class="mb-3 leading-relaxed">
              Photo booth fam kinfolk cold-pressed sriracha leggings jianbing
              microdosing tousled waistcoat.
            </p>
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
            <div
              class="absolute bottom-0 left-0 flex justify-center w-full py-4 mt-2 leading-none text-center"
            >
              <span
                class="inline-flex items-center py-1 pr-3 mr-3 text-sm leading-none text-gray-500 border-r-2 border-gray-700 border-opacity-50"
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
          </div>
        </div>
        <div class="p-4 lg:w-1/3">
          <div
            class="relative h-full px-8 pt-16 pb-24 overflow-hidden text-center bg-gray-800 rounded-lg bg-opacity-40"
          >
            <h2
              class="mb-1 text-xs font-medium tracking-widest text-gray-500 title-font"
            >
              CATEGORY
            </h2>
            <h1
              class="mb-3 text-xl font-medium text-white title-font sm:text-2xl"
            >
              Selvage Poke Waistcoat Godard
            </h1>
            <p class="mb-3 leading-relaxed">
              Photo booth fam kinfolk cold-pressed sriracha leggings jianbing
              microdosing tousled waistcoat.
            </p>
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
            <div
              class="absolute bottom-0 left-0 flex justify-center w-full py-4 mt-2 leading-none text-center"
            >
              <span
                class="inline-flex items-center py-1 pr-3 mr-3 text-sm leading-none text-gray-500 border-r-2 border-gray-700 border-opacity-50"
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
          </div>
        </div>
      </div>
    </div>
  </section>
{/if}
