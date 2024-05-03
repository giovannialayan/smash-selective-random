<script>
  import { createEventDispatcher } from 'svelte';

  const dispatch = createEventDispatcher();

  function handleSelect(id, selected) {
    dispatch('select', {
      selectState: !selected,
      id: id,
    });
  }

  export let name;
  export let selected;
  export let id;
</script>

<button on:click={() => handleSelect(id, selected)}>
  <img
    class="characterImage {!selected ? 'hidden' : ''}"
    src="characters selected/{name} selected.webp"
    alt="{name} active image"
    draggable="false"
  />
  <img
    class="characterImage {selected ? 'hidden' : ''}"
    src="characters unselected/{name} unselected.webp"
    alt="{name} inactive image"
    draggable="false"
  />
</button>

<style>
  .characterImage {
    min-width: 1rem;
  }

  @media (max-width: 576px) {
    .characterImage {
      max-width: 3rem;
    }
  }
</style>
