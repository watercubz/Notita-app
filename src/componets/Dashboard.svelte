<script>
  export let notes;
  import Note from "./Note.svelte";
  import NotePlaceholder from "./NotePlaceholder.svelte";
</script>

<div class="Dashboard">
  <div class="notes-container">
    <NotePlaceholder on:click />
    {#each notes as { color, title, text, id }}
      <Note {color} bind:title bind:text {id} on:update on:color on:remove />
    {/each}
  </div>
</div>

<style>
  .Dashboard {
    width: 100%;
    padding: 20px;
    box-sizing: border-box;
  }
  .notes-container {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    width: 100%;
    gap: 10px;
  }
  @media (max-width: 600px) {
    .notes-container {
      grid-template-columns: repeat(2, 1fr);
    }
  }

  @media (max-width: 400px) {
    .notes-container {
      grid-template-columns: 1fr;
    }
  }
</style>
