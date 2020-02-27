<script>
  import books from './bookdata.js'
  import StoreTitle from './StoreTitle.svelte'
  import Book from './Book.svelte'
</script>

<style>

  .bookshelf {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
    grid-auto-flow: dense
  }
  /* Single column display for phones */
  @media (max-width: 459px) {
    .bookshelf {
      display: flex;
      flex-direction: column
    }
  }

</style>

<StoreTitle/>
<div class="bookshelf">
  {#each books as book}
    <Book data={book}/>
  {/each}
</div>