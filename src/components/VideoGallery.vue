<template>
  <div class="video-gallery">
    <div v-for="(item, key) in videos" :key="key">
      <div class="video-container dark-bg" v-html="generateYouTubeEmbedCode(item.url)"></div>
      <h3>{{ item.title }}</h3>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      videos: [
        // Add YouTube video IDs title description here
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
        { url: 'fYs2Mdyasuc?si=VpZs941UHD_oXuK_', title: 'Usability' },
        { url: 'MkKr2Cc0BuM?si=wpAAbxKViT2xP8ZR', title: 'Business Understanding' },
        { url: 'ULWhr_2CP-g?si=JzpfkV7TY8yAl5Z2', title: 'Market Research' },
        { url: 'DwR0SZTBMTU?si=p54QB5dx8COMAcW_', title: 'Collaboration' },
        { url: '8I3NTE4cn5s?si=bTItTFQX4Bumhogm', title: 'Ethics and Legal Consideration' },
      ]
  } 
    },
    methods: {
      generateYouTubeEmbedCode(videoId) {
      return `<iframe width="350" height="200" src="https://www.youtube.com/embed/${videoId}" frameborder="0" allowfullscreen></iframe><br>`;
    }
  }
};
</script>

<style scoped>
h3 { font-weight:bold; color:#242424; margin-top: 12px;}

.dark-bg { background: black;}
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

.video-container { height: 200px;}
.video-container:hover {
  box-shadow: 7px 7px 13px #b0b0b0;
  height: 200px;
}
@media only screen and (max-width: 1000px) {
    .video-gallery { 
      display:flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      margin: 30px auto 0;
    }
}
</style>


