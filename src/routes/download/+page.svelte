<!-- DownloadButton.svelte -->
<script>
  import { onMount } from 'svelte/internal';
import toast, { Toaster } from 'svelte-french-toast';
  import { saveAs } from 'file-saver';

  import { getAuth } from 'firebase/auth';
  import { app } from '../../firebase';
  import { goto } from '$app/navigation';

  const auth = getAuth(app);
  let user;

  onMount(() => {
    const unsubscribe = auth.onAuthStateChanged((currentUser) => {
      user = currentUser;
      if (!user) {
        goto('/login');
toast.error('Please log in to access this page.');
      }
    });

    return unsubscribe;
  });

  
  
  const downloadFile = () => {
    // Replace 'url_to_your_file' with the actual URL of the file you want to download
    const fileUrl = 'https://webuinet.vercel.app/logo.svg';
    // Replace 'file_name.extension' with the desired name and extension of the file
    const fileName = 'logo.svg';

    fetch(fileUrl)
      .then(response => response.blob())
      .then(blob => saveAs(blob, fileName))
      .catch(error => console.error('Error downloading file:', error));
  };
</script>
<Toaster/>
<div class="section section--content">
		<div class="section__content">

<button class="form__btn" on:click={downloadFile}>Download File</button>
</div>
</div>
