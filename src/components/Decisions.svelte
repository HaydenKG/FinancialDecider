<script lang="ts">
  import { createEventDispatcher } from 'svelte';
  export let value;
  //dispatch needed to notify parent component that value changed
  const dispatch = createEventDispatcher();

  function updateParent() {
    dispatch('updateQuestionValue');
  }
</script>

<input
  name="decisionInput"
  on:change={() => updateParent()}
  type="range"
  min="1"
  max="5"
  bind:value
  class="range range-xs range-primary"
  step="1"
/>
<div class="w-full flex justify-between text-s px-2">
  <!-- <span>1</span>
  <span>2</span>
  <span>3</span>
  <span>4</span>
  <span>5</span> -->
  <span>Yes</span>
  <span />
  <span>Not sure</span>
  <span />
  <span>No</span>
</div>
