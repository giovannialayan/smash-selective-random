<script>
  import { createEventDispatcher } from 'svelte';

  const dispatch = createEventDispatcher();

  function handleClick(e) {
    dispatch('click', e);
  }
</script>

<button id="button" on:click={handleClick} class="bg-gray-700 hover:bg-gray-600 border border-gray-600 text-white py-2 px-4 rounded">
  <slot></slot>
</button>
