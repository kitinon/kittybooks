<script>
  export let data
  import BookInfo from './BookInfo.svelte'
</script>

<style>
  .container {
    display: flex;
    justify-content: flex-start;
    margin: 1% 2% 5% 1%
  }

  .image {
    width: 160px;
    margin-right: 15px
  }
  .image > img { width: 100% }
</style>

<div class="container">
  <div class="image">
    <img src={`/images/${data.id}.jpg`}
          alt={data.title} title={data.title}>
  </div>
  <BookInfo {data}/>
</div>
