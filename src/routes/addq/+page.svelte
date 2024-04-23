<!-- AddQuizData.svelte -->
<script>
  // Import necessary functions from firebase/firestore
  import { onMount } from 'svelte';
  import { collection, addDoc, getFirestore } from 'firebase/firestore';
  import { app } from '../../firebase'; // Assuming you have a firebase.js file

  const db = getFirestore(app); // Initialize Firestore with your Firebase app

  // Function to add quiz data to Firestore
  async function addQuizData() {
    try {
      // Add question 1
      await addDoc(collection(db, "mquiz"), {
        id: "question_1",
        text: "What does CSS stand for?",
        options: [
          { id: "option_a", alphabet: "A", label: "Cascading Style Sheets", icon: "https://res.cloudinary.com/dvhndpbun/image/upload/v1588518387/jdsjkefkefkefefexco.svg" },
          { id: "option_b", alphabet: "B", label: "Creative Screen Styling", icon: "https://res.cloudinary.com/dvhndpbun/image/upload/v1588517753/jfdedgwfzexf4hjin.svg" },
          { id: "option_c", alphabet: "C", label: "Cascading Style Screen", icon: "https://res.cloudinary.com/dvhndpbun/image/upload/v1588517753/jfdedgwfzexf4hjin.svg" }
        ]
      });

      // Add question 2
      await addDoc(collection(db, "quiz"), {
        id: "question_2",
        text: "What is HTML used for?",
        options: [
          { id: "option_a", alphabet: "A", label: "Hypertext Markup Language" },
          { id: "option_b", alphabet: "B", label: "Hyperlink and Text Markup Language" },
          { id: "option_c", alphabet: "C", label: "Home Tool Markup Language" }
        ]
      });

      alert("Quiz data added successfully!");
    } catch (error) {
      console.error("Error adding quiz data: ", error);
    }
  }

  onMount(() => {
    addQuizData(); // Call the function when the component mounts
  });
</script>
