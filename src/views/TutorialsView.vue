<template>
  <Header />
  <div class="tutorials">
    <h1>UX/UI Tutorials</h1>
  </div>
  <div class="video-container">
    <iframe
      width="360"
      height="250"
      src="https://www.youtube.com/embed/VIDEO_ID"
      frameborder="0"
    ></iframe>
    <iframe
      width="360"
      height="250"
      src="https://www.youtube.com/embed/VIDEO_ID"
      frameborder="0"
    ></iframe>
    <iframe
      width="360"
      height="250"
      src="https://www.youtube.com/embed/VIDEO_ID"
      frameborder="0"
    ></iframe>
    <iframe
      width="360"
      height="250"
      src="https://www.youtube.com/embed/VIDEO_ID"
      frameborder="0"
    ></iframe>
    <iframe
      width="360"
      height="250"
      src="https://www.youtube.com/embed/VIDEO_ID"
      frameborder="0"
    ></iframe>
    <iframe
      width="360"
      height="250"
      src="https://www.youtube.com/embed/VIDEO_ID"
      frameborder="0"
    ></iframe>
    <iframe
      width="360"
      height="250"
      src="https://www.youtube.com/embed/VIDEO_ID"
      frameborder="0"
    ></iframe>
    <iframe
      width="360"
      height="250"
      src="https://www.youtube.com/embed/VIDEO_ID"
      frameborder="0"
    ></iframe>
    <iframe
      width="360"
      height="250"
      src="https://www.youtube.com/embed/VIDEO_ID"
      frameborder="0"
    ></iframe>
    <iframe
      width="360"
      height="250"
      src="https://www.youtube.com/embed/VIDEO_ID"
      frameborder="0"
    ></iframe>
    <iframe
      width="360"
      height="250"
      src="https://www.youtube.com/embed/VIDEO_ID"
      frameborder="0"
    ></iframe>
    <iframe
      width="360"
      height="250"
      src="https://www.youtube.com/embed/VIDEO_ID"
      frameborder="0"
    ></iframe>
    <iframe
      width="360"
      height="250"
      src="https://www.youtube.com/embed/VIDEO_ID"
      frameborder="0"
    ></iframe>
    <iframe
      width="360"
      height="250"
      src="https://www.youtube.com/embed/VIDEO_ID"
      frameborder="0"
    ></iframe>
    <iframe
      width="360"
      height="250"
      src="https://www.youtube.com/embed/VIDEO_ID"
      frameborder="0"
    ></iframe>
  </div>
  <Footer />
</template>

<style scoped>

.video-container {
  display: grid;
grid-template-columns: repeat(3, 1fr);
grid-template-rows: repeat(5, 1fr);
grid-column-gap: 0px;
grid-row-gap: 0px;
  position: relative;
  padding-bottom:5%; /* 16:9 aspect ratio */
  height: auto;
  overflow: hidden;
  width: 100%;
}

.video-container iframe {
  /* position: absolute;
  top: 0;
  left: 0; */
  /* width: 100%;
  height: 100%; */
  margin-bottom: 45px;
}

h1 { color: white;text-align: center;font-size: 2.5rem; line-height: 1.25;}
.tutorials {
  display: flex;
    align-items: center;
    justify-content: center;
    color: white;
    /* height: 90vh; */
  }
  .tutorials h1 { padding: 50px 0 30px}

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

export default {
  components: {
    Header,
    Footer
  },
  name: 'VideoPlayer'
}
</script>
