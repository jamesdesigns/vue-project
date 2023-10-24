<template>
  <div class="video-item">
    <video :src="video.url" controls></video>
    <h3>{{ video.title }}</h3>
  </div>
</template>

<script>
export default {
  props: {
    video: {
      type: Object,
      required: true
    }
  }
};
</script>

<style scoped>
.video-item {
  margin: 10px;
  max-width: 300px;
}
</style>
