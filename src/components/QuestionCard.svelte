<script>
  import Decisions from "./Decisions.svelte";
  export let question;
</script>

<div class="card big">
  <h4>{question}</h4>
  <Decisions />
</div>
