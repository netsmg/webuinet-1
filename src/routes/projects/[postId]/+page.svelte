	<script>
  import { onMount } from 'svelte';
  import { getFirestore, doc, getDoc } from 'firebase/firestore';
  import { page } from "$app/stores";
  import { app } from '../../../firebase';

  let post = {};

  onMount(async () => {
    document.title ="loading..";
    const postId = $page.params.postId;
    const db = getFirestore(app);
    const postRef = doc(db, 'blogs', postId);
    const postSnapshot = await getDoc(postRef);
    
    if (postSnapshot.exists()) {
      post = postSnapshot.data();
     document.title = post.title;
    } else {
      console.error('Post not found');
    }
  });
  

</script>
 
  <svelte:head>
  
  <link rel="stylesheet" href="/css/style.css">
  <link rel="stylesheet" href="/css/responsive.css">
</svelte:head>
<div class="col-xl-4">
              <div class="card card-projects">
                <div class="card-body">
  
                  <h3 class="card-title">Projects Details<a class="link-btn" href="/">All Projects
                      <svg class="icon" width="20" height="20" viewBox="0 0 20 20" fill="none"
                        xmlns="http://www.w3.org/2000/svg">
                        <path d="M4.16699 10H15.8337" stroke="#4770FF" stroke-width="1.5" stroke-linecap="round"
                          stroke-linejoin="round" />
        <path d="M10.833 15L15.833 10" stroke="#4770FF" stroke-width="1.5" stroke-linecap="round"
                          stroke-linejoin="round" />
                        <path d="M10.833 5L15.833 10" stroke="#4770FF" stroke-width="1.5" stroke-linecap="round"
                          stroke-linejoin="round" />
                      </svg>
  
                    </a></h3>
                  <div class="projects-main mt-24">
                    <div class="row g-4 parent-container">
                      {#if Object.keys(post).length !== 0}
        
                      
                      <div class="col-lg-12">
                        <div class="project-item">
                          <div class="image">
                            <img src="{post.img}" alt="{post.title}" class="img-fluid w-100">
                            <a href="{post.link}"
                              class="gallery-popup full-image-preview parent-container">
                              <svg class="icon" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="none"
                                stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5">
                                <path d="M10 4.167v11.666M4.167 10h11.666"></path>
                              </svg>
                            </a>
                            <div class="info">
                              <span class="category">{post.title}</span>
                            </div>
                          </div>
                        </div>
                      </div>
                      
                      
                      
  {:else}
    <p>Loading...</p>
  {/if}
                    </div>
                  </div>
                </div>
              </div>
            </div>
        
