class="form__input AddQuestionsForm.svelte -->
<script>
  import { onMount } from 'svelte';
  import { collection, getFirestore, onSnapshot } from 'firebase/firestore';
  import { app } from '../../firebase';
  
  
const db = getFirestore(app);
 let formData = {
    questions: [
      { text: "", options: [{ id: "", alphabet: "", label: "", icon: "" }] }
    ]
  };

  function addQuestion() {
    formData.questions = [...formData.questions, { text: "", options: [{ id: "", alphabet: "", label: "", icon: "" }] }];
  }

  async function handleSubmit() {
    try {
      for (const question of formData.questions) {
        await db.collection("quiz").add(question);
      }
      console.log("Questions added successfully!");
      formData = { questions: [{ text: "", options: [{ id: "", alphabet: "", label: "", icon: "" }] }] }; // Reset form data
    } catch (error) {
      console.error("Error adding questions: ", error);
    }
  }
</script>
<div class="section section--content">
		<div class="section__content">
<h2>Add Quiz Questions</h2>

<form on:submit|preventDefault={handleSubmit}>
  {#each formData.questions as question, i (question.text)}
    <div>
      <label>Question {i + 1}:</label>
    <input type="text" bind:value={question.text} class="form__input" required>
    </div>
    {#each question.options as option, j (option.id)}
      <div class="form__select">
        <label>Option {option.alphabet}:</label>
        <input type="text" bind:value={option.label} class="form__input" required >
      </div>
    {/each}
    <button class="form__btn form__btn--small" type="button" on:click={() => addQuestion()}>Add Option</button>
    {#if i === formData.questions.length - 1}
      <button type="button" on:click={() => formData.questions.splice(i, 1)}>Remove Question</button>
    {/if}
  {/each}
  <button type="submit" class="form__btn form__btn--small">Submit Questions</button>
</form>
</div>
</div>
