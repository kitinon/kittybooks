<script>
  import books from './bookdata.js'
</script>

<style>
  .storetitle {
    display: flex;
    margin-bottom: 20px;
    justify-content: space-between;
  }
  /* Single column display for phones */
  @media (max-width: 459px) {
    .storetitle {
      display: flex;
      flex-direction: column
    }
  }

  .storelogo {
    display: flex;
    height: 80px
  }

  .storelogo > img {
    height: 100%;
    width: auto
  }

  .booksearch {
    display: flex;
    justify-content: center;
    align-items: center
  }
  .booksearch > input {
    width: 320px
  }
  @media (max-width: 459px) {
    .booksearch {
      margin-top: 20px;
    }
  }

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

  .bookholder {
    display: flex;
    justify-content: flex-start;
    margin: 1% 2% 5% 1%
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
  
  .bookinfo > span {
    white-space: nowrap;
    margin-right: 10px;
    color: gray
  }

  .booktitle {
    grid-column: 1 / -1;
    margin-bottom: 5px
  }
</style>

<div class="storetitle">
  <div class="storelogo">
    <img src="/images/kitty.jpg" alt="kitty logo">
    <h1>ร้านคิตตี้บุ๊ค</h1>
  </div>
  <div class="booksearch">
    <input type="search" id="search" name="search">
    <button><i class="fas fa-search fa-lg" aria-hidden="true"></i></button>
  </div>
</div>
<div class="bookshelf">
  {#each books as book}
    <div class="bookholder">
      <div class="bookimage">
        <img src={`/images/${book.id}.jpg`}
             alt={book.title} title={book.title}>
      </div>
      <div class="bookinfo">
        <div class="booktitle"><b>{book.title}</b></div>
        <span>บาร์โค้ด</span>{book.id}
        <span>สำนักพิมพ์</span>{book.publisher}
        <span>ผู้เขียน</span>{book.author}
        <span>ราคา</span>{book.price} บาท
      </div>            
    </div>
  {/each}
</div>