<script>
  export let data
</script>

<style>
  .container {
    display: grid;
    width: 100%;
    grid-template-columns: min-content 1fr;
    grid-auto-rows: min-content;
    font-size: 11.5pt
  }
  
  .container > span {
    white-space: nowrap;
    margin-right: 10px;
    color: gray
  }

  .title {
    grid-column: 1 / -1;
    margin-bottom: 5px
  }
</style>

<div class="container">
  <div class="title"><b>{data.title}</b></div>
  <span>บาร์โค้ด</span>{data.id}
  <span>สำนักพิมพ์</span>{data.publisher}
  <span>ผู้เขียน</span>{data.author}
  <span>ราคา</span>{data.price} บาท
</div>            