<script>
    import { onMount } from 'svelte';
    import ComicImage from '../components/ComicImage.svelte';
  
    let images = [
      '/images/1.png',
      '/images/2.png',
      '/images/3.png', 
      '/images/4.png', 
      '/images/5.png', 
      '/images/6.png', 
      '/images/7.png', 
      '/images/8.png', 
    ];
    let currentImageIndex = 0;
    let currentImage = images[currentImageIndex];
  
    const nextImage = () => {
      currentImageIndex = (currentImageIndex + 1) % images.length;
      currentImage = images[currentImageIndex];
    };
  
    const handleImageClick = () => {
      nextImage();
    };
  
    onMount(() => {
      document.body.addEventListener('keydown', handleKeyPress);
      return () => {
        document.body.removeEventListener('keydown', handleKeyPress);
      };
    });
  
    const handleKeyPress = (event) => {
      if (event.key === 'ArrowRight') {
        nextImage();
      }
    };
  </script>
  
  <main>
    <ComicImage src={currentImage} onClick={handleImageClick} />
  </main>
  
  <style>
    main {
      text-align: center;
    }
  </style>