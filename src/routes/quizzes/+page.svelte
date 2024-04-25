<script>
  import { onMount } from 'svelte';
  import { collection, getFirestore, getDocs } from 'firebase/firestore';
  import { app } from '../../firebase';

  let questions = []; // Initialize the questions array

  onMount(async () => {
    const db = getFirestore(app);
    const querySnapshot = await getDocs(collection(db, 'mquiz'));
    questions = querySnapshot.docs.map(doc => doc.data());
  });
</script>

<div class="home">
  {#if questions.length > 0}
    {#each questions as question, index}
      <div class="intro-box">
        <div class="intro-texts">
          <h1 class="intro-title">{question.title}</h1>
          <p class="intro-description">Choose the quiz you want to solve</p>
        </div>
        <div class="intro-icon">
          <i class="bi bi-question-circle"></i>
        </div>
      </div>
      <div class="level-boxes">
        <div class="level-box">
          <div class="level-text">
            <h2 class="level-name">{question.level}</h2>
            <span>Level</span>
          </div>
          <a class="level-link" href="{question.link}">
            <span>Start Quiz</span> <i class="bi bi-arrow-right"></i>
          </a> <!-- Corrected closing tag -->
        </div>
      </div>
    {/each}
  {:else}
    <p>Loading...</p>
  {/if}
</div>
