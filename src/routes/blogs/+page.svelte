<script>
  import { collection, getFirestore, onSnapshot } from 'firebase/firestore';
  import { app } from '../../firebase';
  
  let blogs = [];
  const db = getFirestore(app);

  const query = collection(db, 'blogs');

  onSnapshot(query, (snapshot) => {
    blogs = snapshot.docs.map(doc => doc.data());
  }, (error) => {
    console.error('Error getting blogs: ', error);
  });
</script>
<section class="section section--first">
		
			<div class="container">
				<div class="row">
{#each blogs as blog (blog.id)}
  <div class="col-12 col-md-6 col-xl-4">
    <div class="post">
      <a href="posts/{blog.id}" class="post__img">
        <img src="{blog.image}" alt="blog image">
      </a>

      <div class="post__content">
        <a href="/" class="post__category">{blog.tag}</a>
            
        <h3 class="post__title"><a href="article.html">{blog.title}</a></h3>
        <div class="post__meta">
          <span class="post__date"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M15,11H13V7a1,1,0,0,0-2,0v5a1,1,0,0,0,1,1h3a1,1,0,0,0,0-2ZM12,2A10,10,0,1,0,22,12,10.01114,10.01114,0,0,0,12,2Zm0,18a8,8,0,1,1,8-8A8.00917,8.00917,0,0,1,12,20Z"/></svg> 9 hours ago</span>
          <span class="post__views"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M21.92,11.6C19.9,6.91,16.1,4,12,4S4.1,6.91,2.08,11.6a1,1,0,0,0,0,.8C4.1,17.09,7.9,20,12,20s7.9-2.91,9.92-7.6A1,1,0,0,0,21.92,11.6ZM12,18c-3.17,0-6.17-2.29-7.9-6C5.83,8.29,8.83,6,12,6s6.17,2.29,7.9,6C18.17,15.71,15.17,18,12,18ZM12,8a4,4,0,1,0,4,4A4,4,0,0,0,12,8Zm0,6a2,2,0,1,1,2-2A2,2,0,0,1,12,14Z"/></svg> {blog.views}</span>
        </div>
      </div>
    </div>
  </div>
{/each}
</div>
</div>
</section>
