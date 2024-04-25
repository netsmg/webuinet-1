<!-- CreateQuiz.svelte -->

<script>
  import { writable } from 'svelte/store';
  import { getFirestore, collection, addDoc } from 'firebase/firestore';
  import { app } from '../firebase'; // Assuming you have your Firebase configuration in firebase.js

  let title = '';
  let level = '';
  let question = '';
  let answer = '';
  let isTrueAnswer = false;
  let answers = writable([]);

  const addAnswer = () => {
    answers.update(arr => [...arr, { answer, trueAnswer: isTrueAnswer }]);
    answer = '';
    isTrueAnswer = false;
  };

  const submitQuiz = async () => {
    const db = getFirestore(app);
    const quizRef = collection(db, 'quizzes');
    const newQuiz = await addDoc(quizRef, { title, level, questions: answers });
    console.log('New quiz added with ID: ', newQuiz.id);
  };
</script>
<div class="section section--content">
		<div class="section__content">
<div>
  <h1>Create a New Quiz</h1>
  <label for="title">Title:</label>
   <input type="text" class="form__input" id="title" bind:value={title}>

  <label for="level">Level:</label>
  <input type="text" class="form__input" id="level" bind:value={level}>

  <h2>Questions</h2>
  <label for="question">Question:</label>
  <input type="text" class="form__input" id="question" bind:value={question}>

  <h3>Answers</h3>
  <label for="answer">Answer:</label>
  <input class="form__input" type="text" id="answer" bind:value={answer}>
  <input type="checkbox" bind:checked={isTrueAnswer}>
  <label for="isTrueAnswer">Is True Answer</label>
  <button class="class="form__btn form__btn--small" type="submit" on:click={addAnswer}>Add Answer</button>

  <ul>
    {#each $answers as { answer, trueAnswer }, index}
      <li>{index + 1}. {answer} {#if trueAnswer}(Correct answer){/if}</li>
    {/each}
  </ul>

  <button class="form__btn form__btn--small" type="submit" on:click={submitQuiz}>Submit Quiz</button>
</div>

</div>
</div>
