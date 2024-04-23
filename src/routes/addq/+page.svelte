<script>
  import { onMount } from 'svelte';
  import { collection, addDoc, getFirestore } from 'firebase/firestore';
  import { app } from '../../firebase'; // Assuming you have a firebase.js file
  
  const db = getFirestore(app);

  let question1 = '';
  let question2 = '';
  let option1a = '';
  let option1b = '';
  let option1c = '';
  let option2a = '';
  let option2b = '';
  let option2c = '';

  async function addQuizData() {
    try {
      await addDoc(collection(db, "mquiz"), {
        id: "question_1",
        text: question1,
        options: [
          { id: "option_a", alphabet: "A", label: option1a },
          { id: "option_b", alphabet: "B", label: option1b },
          { id: "option_c", alphabet: "C", label: option1c }
        ]
      });

      await addDoc(collection(db, "mquiz"), {
        id: "question_2",
        text: question2,
        options: [
          { id: "option_a", alphabet: "A", label: option2a },
          { id: "option_b", alphabet: "B", label: option2b },
          { id: "option_c", alphabet: "C", label: option2c }
        ]
      });

      alert("Quiz data added successfully!");
    } catch (error) {
      console.error("Error adding quiz data: ", error);
    }
  }

  onMount(() => {
    addQuizData();
  });
</script>
<div class="section section--content">
		<div class="section__content">
<form on:submit|preventDefault="{addQuizData}">
  <label>
    Question 1:
    <input bind:value="{question1}"  class="form__input" type="text">
  </label>
  <label>
    Option 1A:
    <input bind:value="{option1a}" class="form__input" type="text">
  </label>
  <label>
    Option 1B:
    <input bind:value="{option1b}" class="form__input" type="text">
  </label>
  <label>
    Option 1C:
    <input bind:value="{option1c}" class="form__input"  type="text">
  </label>
  <label>
    Question 2:
    <input bind:value="{question2}" class="form__input" type="text">
  </label>
  <label>
    Option 2A:
    <input bind:value="{option2a}" class="form__input" type="text">
  </label>
  <label>
    Option 2B:
    <input bind:value="{option2b}" class="form__input" type="text">
  </label>
  <label>
    Option 2C:
    <input bind:value="{option2c}" class="form__input" type="text">
  </label>
  <button class="form__btn form__btn--small" type="submit">Add Quiz Data</button>
</form>
</div>
</div>
