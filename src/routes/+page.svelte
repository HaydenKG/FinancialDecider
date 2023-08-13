<script>
  import SmallCard from "../components/SmallCard.svelte";
</script>

<h1>Home</h1>
<div class="box">
  <a href="/stock">
    <SmallCard imgSrc={"./"} title="Stocks" />
  </a>
  <SmallCard imgSrc={"./"} title="ETFs" />
</div>
