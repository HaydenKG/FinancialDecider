<script>
  import SmallCard from "./SmallCard.svelte";
  export let decisionHandler = (value) => {
    console.log(value);
  };
</script>

<div class="box">
  <button class="success" onclick={() => decisionHandler(5)}>Yes</button><button
    onclick={() => decisionHandler(0)}>Unsure</button
  ><button class="warn" onclick={() => decisionHandler(-5)}>No</button>
</div>

<style>
</style>
