<!-- PostDetails.svelte -->
<script>
  import { onMount } from 'svelte';
  import { doc, getDoc, getFirestore } from 'firebase/firestore';
   
  import { app } from '../../firebase';

  let post = {};
  const db = getFirestore(app);

  onMount(async () => {
    // Get the post ID from the URL parameter
    const urlParams = new URLSearchParams(window.location.search);
    const postId = urlParams.get('id');
    
    const postRef = doc(db, 'blogs', postId);

    try {
      const docSnap = await getDoc(postRef);
      if (docSnap.exists()) {
        post = docSnap.data();
      } else {
        console.log('No such document!');
      }
    } catch (error) {
      console.log('Error getting document:', error);
    }
  });
</script>

<div class="post-details">
  {#if Object.keys(post).length > 0}
    <h1>{post.title}</h1>
    <div>{post.content}</div>
    <!-- Add other post details here -->
  {:else}
    <p>Loading...</p>
  {/if}
</div>
