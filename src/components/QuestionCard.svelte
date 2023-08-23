<script lang="ts">
  import Decisions from './Decisions.svelte';
  import type { QuestionType } from '../types.svelte';
  export let question: QuestionType;

  function valueChanged() {
    //reassign in order for svelte to update object
    question = question;
  }
</script>

<div class="card w-96 shadow-md">
  <div class="card-body items-center text-center">
    <h4 class="card-title">{question.question}</h4>
    <div class="flex w-full flex-col">
      <!-- binding needed to react to updates in child component -->
      <Decisions
        on:updateQuestionValue={() => valueChanged()}
        bind:value={question.value}
      />
    </div>
  </div>
</div>
