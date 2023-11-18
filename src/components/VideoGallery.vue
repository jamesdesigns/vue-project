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
    <!-- <div v-for="videoTitle in videoTitles" :key="videoTitle">
      <div v-html="generateYouTubeTitle(videoTitle)"></div>
    </div> -->
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
      videoIds: ['kbZejnPXyLM?si=Iu8hmadPtfMTynz3','SRec90j6lTY?si=aJVpNhfCt5E6vzrB', 'rYH7AErVd7w?si=_YAEGfSMLmDIStnc','t0aCoqXKFOU?si=j9IZqmkzSp8hPCbD','TgqeRTwZvIo?si=GVf2f_d2rUW36jd7','c9Wg6Cb_YlU?si=n8m_HCn0QXpmMIeC','an5LH3K44ks?si=aSOujKAemhAyoZ8c','BZ0QER_0ZWI?si=rs5Sw7yq9qYQz4cx','uL2ZB7XXIgg?si=UteNqhgxzbU7wksA','D4NyQ5iOMF0?si=0eFiyg6-NFRJDwgx','fYs2Mdyasuc?si=VpZs941UHD_oXuK_','MkKr2Cc0BuM?si=wpAAbxKViT2xP8ZR'],
      videoTitles: ['User Research', 'Information Architecture', 'User Personas', 'User Journey Mapping', 'Visual Design', 'Prototyping', 'Interaction Design', 'Responsive Design', 'Cognitive Psychology', 'Emotional Design', 'Usability', 'Business Understanding', 'Market Research', 'Collaboration', 'Ethics and Legal Consideration'],
      videos: [
        // Add video URLs or other information here
        { url: 'kbZejnPXyLM?si=Iu8hmadPtfMTynz3', title: 'User Research' },
        { url: 'SRec90j6lTY?si=aJVpNhfCt5E6vzrB', title: 'Information Architecture' },
        { url: 'rYH7AErVd7w?si=_YAEGfSMLmDIStnc', title: 'User Personas' },
        { url: 't0aCoqXKFOU?si=j9IZqmkzSp8hPCbD', title: 'User Journey Mapping' },
        { url: 'TgqeRTwZvIo?si=GVf2f_d2rUW36jd7', title: 'Visual Design' },
        { url: 'c9Wg6Cb_YlU?si=n8m_HCn0QXpmMIeC', title: 'Prototyping' },
        { url: 'an5LH3K44ks?si=aSOujKAemhAyoZ8c', title: 'Interaction Design' },
        { url: 'BZ0QER_0ZWI?si=rs5Sw7yq9qYQz4cx', title: 'Responsive Design' },
        { url: 'uL2ZB7XXIgg?si=UteNqhgxzbU7wksA', title: 'Cognitive Psychology' },
        { url: 'D4NyQ5iOMF0?si=0eFiyg6-NFRJDwgx', title: 'Emotional Design' },
        { url: 'D4NyQ5iOMF0?si=0eFiyg6-NFRJDwgx', title: 'Usability' },
        { url: 'D4NyQ5iOMF0?si=0eFiyg6-NFRJDwgx', title: 'Business Understanding' },
        { url: 'D4NyQ5iOMF0?si=0eFiyg6-NFRJDwgx', title: 'Market Research' },
        { url: 'D4NyQ5iOMF0?si=0eFiyg6-NFRJDwgx', title: 'Collaboration' },
        { url: 'D4NyQ5iOMF0?si=0eFiyg6-NFRJDwgx', title: 'Ethics and Legal Consideration' }
      ]
  } 
    },
    methods: {
      generateYouTubeEmbedCode(videoId,videoTitle) {
      return `<iframe width="350" height="200" src="https://www.youtube.com/embed/${videoId}" frameborder="0" allowfullscreen></iframe><br><h3>${videoTitle}</h3>`;
    },
    generateYouTubeTitle(videoTitle) {
      return `<h3>${videoTitle}</h3>`;
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


