<script>
  import { createEventDispatcher, onMount, afterUpdate } from 'svelte';

  const dispatch = createEventDispatcher();

  export let options = [];
  let openMenu = false;

  function handleDropdownChange(optionIndex) {
    dispatch('dropdownChange', { optionIndex });
    openMenu = false;
  }

  function handleDropdownDelete(optionIndex) {
    dispatch('dropdownDelete', { optionIndex });
    openMenu = false;
  }

  let buttonElement;

  onMount(() => {
    buttonElement = document.querySelector('#menu-button');
  });

  afterUpdate(() => {
    if (openMenu) {
      buttonElement.scrollIntoView({
        behavior: 'smooth',
      });
    }
  });

  function toggleMenu() {
    openMenu = !openMenu;
  }
</script>

<div class="relative inline-block text-left {options.length == 0 ? 'hidden' : ''}">
  <div>
    <button
      type="button"
      class="inline-flex w-full justify-center gap-x-1.5 bg-gray-700 hover:bg-gray-600 text-white border border-gray-600 rounded-md px-3 py-2 text-sm"
      id="menu-button"
      aria-expanded="true"
      aria-haspopup="true"
      on:click={toggleMenu}
    >
      <slot />
      <svg class="-mr-1 h-5 w-5 text-white" viewBox="0 0 20 20" fill="currentColor" aria-hidden="true">
        <path
          fill-rule="evenodd"
          d="M5.23 7.21a.75.75 0 011.06.02L10 11.168l3.71-3.938a.75.75 0 111.08 1.04l-4.25 4.5a.75.75 0 01-1.08 0l-4.25-4.5a.75.75 0 01.02-1.06z"
          clip-rule="evenodd"
        />
      </svg>
    </button>
  </div>

  <!--
    Dropdown menu, show/hide based on menu state.

    Entering: "transition ease-out duration-100"
      From: "transform opacity-0 scale-95"
      To: "transform opacity-100 scale-100"
    Leaving: "transition ease-in duration-75"
      From: "transform opacity-100 scale-100"
      To: "transform opacity-0 scale-95"
  -->
  <div
    class="absolute right-1/2 translate-x-1/2 z-10 mt-2 w-56 rounded-md bg-gray-700 shadow-lg ring-1 ring-black ring-opacity-5 focus:outline-none
    {openMenu ? '' : 'hidden'}"
    role="menu"
    aria-orientation="vertical"
    aria-labelledby="menu-button"
    tabindex="-1"
  >
    <div class="py-1" role="none">
      <!-- Active: "bg-gray-100 text-gray-900", Not Active: "text-gray-700" -->
      {#each options as option, i}
        <div class="flex flex-row">
          <button
            on:click={() => handleDropdownChange(i)}
            class="block w-full px-4 py-2 text-sm text-white hover:bg-gray-600 text-left"
            role="menuitem"
          >
            {option}
          </button>
          <button on:click={() => handleDropdownDelete(i)} class="block px-4 py-2 text-sm text-white hover:bg-gray-600 text-center"> X </button>
        </div>
      {/each}
    </div>
  </div>
</div>
