<template>
  <Header />
  <div class="tutorials">
    <h1>UX/UI Tutorials</h1>
  </div>
  <div class="video-container">
    <VideoGallery />
  </div>
  <Footer />
</template>

<style scoped>

.video-container iframe {
  margin-bottom: 45px;
}

h1 { color: #090909;text-align: center;font-size: 2.5rem; line-height: 1.25;}

.tutorials {
  display: flex;
    align-items: center;
    justify-content: center;
    color: #090909;
  }
  .tutorials h1 { padding: 50px 0 0;}

  @media only screen and (max-width: 1000px) {
    .video-container { 
      display:flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      margin: 0 auto;
    }
}
</style>

<script>
import Header from "@/components/Header.vue";
import Footer from "@/components/Footer.vue";
import VideoGallery from '@/components/VideoGallery.vue';

export default {
  components: {
    Header,
    VideoGallery,
    Footer
  },
  name: 'VideoPlayer'
}
</script>
