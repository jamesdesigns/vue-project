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
        { url: 'https://example.com/video1.mp4', title: 'Video 1' },
        { url: 'https://example.com/video2.mp4', title: 'Video 2' },
        { url: 'https://example.com/video1.mp4', title: 'Video 3' },
        { url: 'https://example.com/video2.mp4', title: 'Video 4' },
        { url: 'https://example.com/video1.mp4', title: 'Video 5' },
        { url: 'https://example.com/video2.mp4', title: 'Video 6' },
        { url: 'https://example.com/video1.mp4', title: 'Video 7' },
        { url: 'https://example.com/video2.mp4', title: 'Video 8' },
        { url: 'https://example.com/video1.mp4', title: 'Video 9' },
        { url: 'https://example.com/video2.mp4', title: 'Video 10' },
        { url: 'https://example.com/video1.mp4', title: 'Video 11' },
        { url: 'https://example.com/video2.mp4', title: 'Video 12' },
        { url: 'https://example.com/video1.mp4', title: 'Video 13' },
        { url: 'https://example.com/video2.mp4', title: 'Video 14' },
        { url: 'https://example.com/video1.mp4', title: 'Video 15' }
      ]
    };
  }
};
</script>

<style scoped>
.video-gallery {
  /* display: flex;
  flex-wrap: wrap; */
  display: grid;
grid-template-columns: repeat(3, 1fr);
grid-template-rows: repeat(5, 1fr);
grid-column-gap: 0px;
grid-row-gap: 0px;
  position: relative;
  padding-bottom:5%; 
  height: auto;
  overflow: hidden;
  width: 100%;
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
