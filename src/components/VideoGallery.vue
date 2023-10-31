<template>
  <div class="video-gallery">
    <VideoItem
      v-for="(video, index) in videos"
      :key="index"
      :video="video"
    />
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
      videos: [
        // Add video URLs or other information here
        { url: 'https://www.youtube.com/watch?v=TJg3lFaSlSI', title: 'User Research' },
        { url: 'https://example.com/video2.mp4', title: 'Information Architecture' },
        { url: 'https://example.com/video1.mp4', title: 'User Personas' },
        { url: 'https://example.com/video2.mp4', title: 'User Journey Mapping' },
        { url: 'https://example.com/video1.mp4', title: 'Visual Design' },
        { url: 'https://example.com/video2.mp4', title: 'Prototyping' },
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
    };
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
