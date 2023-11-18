<template>
  <!-- <div v-for="videoId in videoIds" :key="videoId" class="video-gallery"> -->
  <div class="video-gallery">
    <VideoItem
      v-for="(video, index) in videos"
      :key="index"
      :video="video"
      v-html="generateYouTubeEmbedCode(videoId)"
    />
    <!-- <div v-html="generateYouTubeEmbedCode(videoId)" class="video-embed"></div> -->
  </div>
</template>

<script>
import VideoItem from './VideoItem.vue';

export default {
  components: {
    VideoItem
  },
  data() {
    return {
      // Hardcoded YouTube video IDs
      videoIds: ['evfFiXNfMGU?si=tZtgI8GtyKKbEhvn', 'evfFiXNfMGU?si=tZtgI8GtyKKbEhvn', 'evfFiXNfMGU?si=tZtgI8GtyKKbEhvn','TgqeRTwZvIo?si=GVf2f_d2rUW36jd7','TgqeRTwZvIo?si=GVf2f_d2rUW36jd7','TgqeRTwZvIo?si=GVf2f_d2rUW36jd7'],
      videos: [
        // Add video URLs or other information here
        { index: 'evfFiXNfMGU?si=tZtgI8GtyKKbEhvn', url: 'evfFiXNfMGU?si=tZtgI8GtyKKbEhvn', title: 'User Research' },
        { url: 'evfFiXNfMGU?si=tZtgI8GtyKKbEhvn', title: 'Information Architecture' },
        { url: 'evfFiXNfMGU?si=tZtgI8GtyKKbEhvn', title: 'User Personas' },
        { url: 'TgqeRTwZvIo?si=GVf2f_d2rUW36jd7', title: 'User Journey Mapping' },
        { url: 'TgqeRTwZvIo?si=GVf2f_d2rUW36jd7', title: 'Visual Design' },
        { url: 'TgqeRTwZvIo?si=GVf2f_d2rUW36jd7', title: 'Prototyping' },
        { url: 'https://example.com/video1.mp4', title: 'Interaction Design' },
        { url: 'https://example.com/video2.mp4', title: 'Responsive Design' },
        { url: 'https://example.com/video1.mp4', title: 'Cognitive Psychology' },
        { url: 'https://example.com/video2.mp4', title: 'Emotional Design' },
        { url: 'https://example.com/video1.mp4', title: 'Usability' },
        { url: 'https://example.com/video2.mp4', title: 'Business Understanding' },
        { url: 'https://example.com/video1.mp4', title: 'Market Research' },
        { url: 'https://example.com/video2.mp4', title: 'Collaboration' },
        { url: 'https://example.com/video1.mp4', title: 'Ethics and Legal Consideration' }
      ]
  } 
    },
    methods: {
      generateYouTubeEmbedCode(videoId) {
      return `<iframe width="350" height="200" src="https://www.youtube.com/embed/${videoId}" frameborder="0" allowfullscreen></iframe>`;
    },
  }
};
</script>

<style scoped>
.video-gallery {
  display: grid; 
  grid-template-columns: repeat(3, 1fr);
  grid-template-rows: repeat(5, 1fr);
  grid-column-gap: 0px;
  grid-row-gap: 0px;
  justify-items: center;
  position: relative;
  padding-bottom:5%; 
  height: auto;
  overflow: hidden;
  width: 100%;
  margin-top:30px;
}
@media only screen and (max-width: 1000px) {
    .video-gallery { 
      display:flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      margin: 0 auto;
    }
}
</style>


