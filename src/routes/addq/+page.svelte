<!-- AddQuizData.svelte -->
<script>
  import { onMount } from 'svelte';
  import { collection, getFirestore, onSnapshot } from 'firebase/firestore';
  import { app } from '../../firebase';
  
  
const db = getFirestore(app);

  // Function to add quiz data to Firestore
  async function addQuizData() {
    try {
      // Add question 1
      await db.collection("quiz").doc("question_1").set({
        text: "What does CSS stand for?",
        options: [
          { id: "option_a", alphabet: "A", label: "Cascading Style Sheets", icon: "https://res.cloudinary.com/dvhndpbun/image/upload/v1588518387/jdsjkefkefkefefexco.svg" },
          { id: "option_b", alphabet: "B", label: "Creative Screen Styling", icon: "https://res.cloudinary.com/dvhndpbun/image/upload/v1588517753/jfdedgwfzexf4hjin.svg" },
          { id: "option_c", alphabet: "C", label: "Cascading Style Screen", icon: "https://res.cloudinary.com/dvhndpbun/image/upload/v1588517753/jfdedgwfzexf4hjin.svg" }
        ]
      });

      // Add question 2
      await db.collection("quiz").doc("question_2").set({
        text: "What is HTML used for?",
        options: [
          { id: "option_a", alphabet: "A", label: "Hypertext Markup Language" },
          { id: "option_b", alphabet: "B", label: "Hyperlink and Text Markup Language" },
          { id: "option_c", alphabet: "C", label: "Home Tool Markup Language" }
        ]
      });

      console.log("Quiz data added successfully!");
    } catch (error) {
      console.error("Error adding quiz data: ", error);
    }
  }

  onMount(() => {
    addQuizData();
  });
</script>
