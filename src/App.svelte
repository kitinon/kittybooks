<script>
  import books from './bookdata.js'
</script>

<style>
  .storetitle {
    display: flex;
    margin-bottom: 20px
  }

  .storetitle > img {
    height: 80px;
  }

  .bookshelf {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
    grid-gap: 32px;
    grid-auto-flow: dense
  }

  .bookholder {
    display: flex;
    justify-content: flex-start
  }

  .bookimage {
    width: 160px;
    margin-right: 15px
  }
  .bookimage > img { width: 100% }

  .bookinfo {
    display: grid;
    width: 100%;
    grid-template-columns: min-content 1fr;
    grid-auto-rows: min-content;
    font-size: 11.5pt
  }
  
  .bookinfo > nobr {
    margin-right: 10px;
    color: gray
  }

  .booktitle {
    grid-column: 1 / -1;
    margin-bottom: 5px
  }
</style>

<div class="storetitle">
  <img src="/images/kitty.jpg" alt="kitty logo">
  <h1>ร้านคิตตี้บุ๊ค</h1>
</div>
<div class="bookshelf">
  {#each books as book}
    <div class="bookholder">
      <div class="bookimage">
        <img src={`/images/${book.id}.jpg`}
             alt={book.title} title={book.title}>
      </div>
      <div class="bookinfo">
        <span class="booktitle"><b>{book.title}</b></span>
        <nobr>บาร์โค้ด</nobr>{book.id}
        <nobr>สำนักพิมพ์</nobr>{book.publisher}
        <nobr>ผู้เขียน</nobr>{book.author}
        <nobr>ราคา</nobr>{book.price} บาท
      </div>            
    </div>
  {/each}
</div>
<!--
.bookshelf {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
    grid-gap: 32px;
    grid-auto-flow: dense;
}
.bookshelf {
  display: flex;
  flex-wrap: wrap;
  background-color: darkgray
}
-->
