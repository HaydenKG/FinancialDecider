<script lang="ts">
  import QuestionCard from '../../components/QuestionCard.svelte';
  import type { QuestionType } from '../../types.svelte';

  const questions: QuestionType[] = [
    {
      question:
        'Is there a trend of the stock being cheaper at certain times of the day?',
      value: 3,
    },
    {
      question: 'Are you planning on buying during the cheaper time?',
      value: 3,
    },
    {
      question:
        'Are there currently any news on the geographical location the company is located at (politically, war and resources)',
      value: 3,
    },
    {
      question:
        'Are there any good news from the company or field they are operating in?',
      value: 3,
    },
    { question: 'Are you certain that the upside will come?', value: 3 },
    { question: 'Are they about to release something of value?', value: 3 },
  ];

  $: currentScore = Object.values(questions).reduce(
    (total, { value }) => total + value,
    0
  );

  $: scoreJudgement = currentScore / 5;
</script>

<div class="flex flex-col w-full items-center gap-5">
  <h1 class="text-3xl">Stock decision</h1>
  {#each questions as question}
    <!-- binding needed to react to updates in child components -->
    <QuestionCard bind:question />
  {/each}
  <h3 class="font-medium">Result:</h3>
  <p>
    Current score <span>
      <!-- assign conditional class depending on value -->
      {currentScore}
    </span>
  </p>
  <p>
    Current score judgement: {scoreJudgement}
    Questions length : {questions.length}
    Your decision seems to be {#if scoreJudgement >= 0.75}
      <span>solid</span>
    {:else if scoreJudgement >= 0.5}
      <span>unsure</span>
    {:else}
      <span>not recommended</span>{/if}
  </p>
</div>

<p>Include transition to next conditional card</p>
<p>Include progress bar?</p>
