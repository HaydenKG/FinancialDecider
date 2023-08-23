<script>
  import SmallCard from '../components/SmallCard.svelte';
</script>

<div class="flex flex-col items-center">
  <h1 class="text-2xl">Home</h1>
  <div class="columns-2">
    <a href="/stock">
      <SmallCard title="Stocks" />
    </a>
    <SmallCard title="ETFs" />
  </div>
</div>
