<!-- DownloadButton.svelte -->
<script>
  import { saveAs } from 'file-saver';

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
<div class="section section--content">
		<div class="section__content">

<button class="form__btn" on:click={downloadFile}>Download File</button>
</div>
</div>
