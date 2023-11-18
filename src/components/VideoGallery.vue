<template>
  <!-- <div v-for="videoId in videoIds" :key="videoId" class="video-gallery"> -->
  <div class="video-gallery">
    <!-- <VideoItem
      v-for="(video, index) in videos"
      :key="index"
      :video="video"
    /> -->
    <div v-for="videoId in videoIds" :key="videoId">
      <div v-html="generateYouTubeEmbedCode(videoId)" class="video-embed"></div>
    </div>
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
      videoIds: ['kbZejnPXyLM?si=Iu8hmadPtfMTynz3', 'SRec90j6lTY?si=aJVpNhfCt5E6vzrB', 'rYH7AErVd7w?si=_YAEGfSMLmDIStnc','t0aCoqXKFOU?si=j9IZqmkzSp8hPCbD','TgqeRTwZvIo?si=GVf2f_d2rUW36jd7','c9Wg6Cb_YlU?si=n8m_HCn0QXpmMIeC','an5LH3K44ks?si=aSOujKAemhAyoZ8c','BZ0QER_0ZWI?si=rs5Sw7yq9qYQz4cx','uL2ZB7XXIgg?si=UteNqhgxzbU7wksA','D4NyQ5iOMF0?si=0eFiyg6-NFRJDwgx','fYs2Mdyasuc?si=VpZs941UHD_oXuK_','MkKr2Cc0BuM?si=wpAAbxKViT2xP8ZR'],
      videos: [
        // Add video URLs or other information here
        { url: 'https://example.com/video1.mp4', title: 'User Research' },
        { url: 'https://example.com/video1.mp4', title: 'Information Architecture' },
        { url: 'https://example.com/video1.mp4', title: 'User Personas' },
        { url: 'https://example.com/video1.mp4', title: 'User Journey Mapping' },
        { url: 'https://example.com/video1.mp4', title: 'Visual Design' },
        { url: 'https://example.com/video1.mp4', title: 'Prototyping' },
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
      return `<iframe width="350" height="200" src="https://www.youtube.com/embed/${videoId}" frameborder="0" allowfullscreen></iframe><br><h3>Title</h3>`;
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
  grid-row-gap: 35px;
  justify-items: center;
  position: relative;
  padding-bottom:5%; 
  height: auto;
  overflow: hidden;
  width: 100%;
  margin-top:30px;
  color: white;
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


