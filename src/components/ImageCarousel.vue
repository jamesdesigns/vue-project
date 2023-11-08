<template>
  <div class="carousel">
    <button @click="prev">Previous</button>
    <div class="viewport">
      <div class="carousel-inner" :style="{ transform: `translateX(-${currentIndex * slideWidth}px)` }">
        <div v-for="(item, index) in items" :key="index" class="slide">
          <img :src="item.url" alt="Slide" />
        </div>
      </div>
    </div>
    <button @click="next">Next</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      currentIndex: 0,
      slideWidth: 300, // Adjust this to match the width of your individual slides
      items: [
        { url: 'image1.jpg' },
        { url: 'image2.jpg' },
        { url: 'image3.jpg' },
        { url: 'image4.jpg' },
        { url: 'image5.jpg' }
      ]
    };
  },
  methods: {
    prev() {
      if (this.currentIndex > 0) {
        this.currentIndex--;
      }
    },
    next() {
      if (this.currentIndex < this.items.length - 3) {
        this.currentIndex++;
      }
    }
  }
};
</script>

<style scoped>
.carousel {
  display: flex;
  align-items: center;
  justify-content: space-between;
  max-width: 800px;
  margin: 0 auto;
}

.viewport {
  overflow: hidden;
  width: 700px; /* Adjust this to match the width of your viewport */
  margin-bottom: 90px;
}

.carousel-inner {
  display: flex;
  transition: transform 0.3s ease-in-out;
}

.slide {
  flex: 0 0 auto;
  margin-right: 10px; /* Adjust as needed for spacing between slides */
  width: 200px;
  height: 200px;
  background-color: white;
  margin: 0 15px;
}

img {
  max-width: 100%;
  height: auto;
}
</style>
