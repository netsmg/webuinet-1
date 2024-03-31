<!-- PostDetails.svelte -->
<script>
  import { onMount } from 'svelte';
  import { getFirestore, doc, getDoc } from 'firebase/firestore';
  import { app } from '../../firebase';

  let post = {};

  onMount(async () => {
    const postId = $page.params.postId;
    const db = getFirestore(app);
    const postRef = doc(db, 'blogs', postId);
    const postSnapshot = await getDoc(postRef);
    
    if (postSnapshot.exists()) {
      post = postSnapshot.data();
    } else {
      console.error('Post not found');
    }
  });
</script>

<div>
  {#if Object.keys(post).length !== 0}
    <h1>{post.title}</h1>
    <img src="{post.image}" alt="Post Image">
    <p>{post.content}</p>
    <!-- Add more details here -->
  {:else}
    <p>Loading...</p>
  {/if}
</div>
