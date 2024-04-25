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
<style>
@import url("https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800;900&display=swap");
@import url("https://cdn.jsdelivr.net/npm/bootstrap-icons@1.10.3/font/bootstrap-icons.css");

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "Inter", sans-serif;
}
:root {
  --first-color: #6a5ae2;
  --opacity-first: #796ae3;
  --second-color: #ff8fa3;
  --opacity-second: #fea5b5;
  --text-color: #ffffff;
  --dark-color: #0c0a2b;
  --light-color: #d2cef6;
  --bg-color: #e8e5fb;
  --body-bg: #ffffff;
  --value: attr(data-value);
}
.app-container {
  width: 100%;
  padding: 2rem 1rem;
  height: 100vh;
  background-color: var(--body-bg);
}
.error-link {
  width: 300px;
  margin: 2rem auto 0 auto;
  display: flex;
  gap: 0.5rem;
  justify-content: center;
  align-items: center;
  padding: 1rem 1.5rem;
  border-radius: 0.5rem;
  color: var(--text-color);
  text-decoration: none;
  background-color: var(--second-color);
}
@media screen and (max-width: 768px) {
  .app-container {
    padding: 0;
  }
}
.intro-box {
  position: relative;
  display: grid;
  grid-template-columns: calc(100% - 70px) 70px;
  gap: 0.5rem;
  align-items: center;
  background-color: var(--first-color);
  border-radius: 1rem;
  padding: 1.5rem 2rem;
  overflow: hidden;
}
.intro-box::before {
  content: "";
  position: absolute;
  left: 40%;
  bottom: -25px;
  width: 55px;
  height: 55px;
  border-radius: 50%;
  border: 7px solid var(--opacity-first);
  z-index: 0;
}
.intro-box::after {
  content: "";
  position: absolute;
  left: -25px;
  top: -25px;
  width: 100px;
  height: 100px;
  border-radius: 50%;
  background-color: var(--opacity-first);
  z-index: 0;
}
.intro-texts {
  z-index: 9;
}
.intro-title {
  font-size: 0.75rem;
  text-transform: uppercase;
  letter-spacing: 2px;
  color: var(--light-color);
  font-weight: 400;
  margin-bottom: 0.5rem;
}
.intro-description {
  font-size: 1rem;
  color: var(--text-color);
}
.intro-icon {
  width: 50px;
  height: 50px;
  display: grid;
  place-items: center;
  border-radius: 0.5rem;
  background-color: var(--opacity-first);
  z-index: 9;
}
.intro-icon i {
  font-size: 1.25rem;
  color: var(--text-color);
}
.level-boxes {
  margin-top: 1rem;
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 0.75rem;
}
.level-box {
  width: 100%;
  border-radius: 1rem;
  background-color: var(--second-color);
  padding: 1rem;
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}
.level-text {
  display: flex;
  flex-direction: column;
  gap: 0.25rem;
  justify-content: center;
  align-items: center;
}
.level-name {
  font-size: 2rem;
  color: var(--text-color);
  font-weight: 600;
}
.level-text span {
  font-size: 0.75rem;
  text-transform: uppercase;
  letter-spacing: 2px;
  color: var(--text-color);
}
.level-link {
  display: inline-block;
  display: flex;
  justify-content: center;
  gap: 0.5rem;
  align-items: center;
  width: 100%;
  text-align: center;
  font-size: 0.9rem;
  border-radius: 0.5rem;
  background-color: var(--opacity-second);
  padding: 0.75rem;
  text-decoration: none;
  color: var(--text-color);
}
</style>
