<script>
	export let books;
</script>

{#if books.length > 0}
	<div class="bookholder">
		<div class="bookimage">
			<img src={`/images/${books[0].id}.jpg`}
						alt={books[0].title} title={books[0].title}>
		</div>
		<div class="bookinfo">
			<div class="booktitle"><b>{books[0].title}</b></div>
			<span>บาร์โค้ด</span>{books[0].id}
			<span>สำนักพิมพ์</span>{books[0].publisher}
			<span>ผู้เขียน</span>{books[0].author}
			<span>ราคา</span>{books[0].price} บาท
		</div>            
	</div>
	<svelte:self books="{books.splice(1)}"/>
{/if}