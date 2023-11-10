<template>
  <div class="carousel">
    <button class="previous-btn" @click="prev">Previous</button>
    <div class="viewport">
      <div class="carousel-inner" :style="{ transform: `translateX(-${currentIndex * slideWidth}px)` }">
        <div v-for="(item, index) in items" :key="index" class="slide">
          <img class="slide-img" :src="item.url" alt="Slide" />
        </div>
      </div>
    </div>
    <button class="next-btn" @click="next">Next</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      currentIndex: 0,
      slideWidth: 300, // Adjust this to match the width of your individual slides
      items: [
        { url: 'https://dreamwalk.com.au/wp-content/uploads/2022/02/app-ui-design-with-rounded-corners.jpeg' },
        { url: 'https://cdn.dribbble.com/userupload/4173059/file/original-1aebd83221dfcb583799b43de30c4621.png?resize=400x0' },
        { url: 'https://cdn.dribbble.com/users/1332195/screenshots/9651082/media/24f62b568b5385a7e43de5e0676a5fac.jpg?resize=400x0' },
        { url: 'https://www.mindinventory.com/blog/wp-content/uploads/2022/10/beauty-app-1024x768.png' },
        { url: 'https://lollypop.design/wp-content/uploads/2023/04/tinywow_Scene-1_20415612.webp' },
        { url: 'https://pledrelms.s3.us-east-2.amazonaws.com/pledre-files/course-image/5fa067e3afe9810007362011/6346cc846507350007a6b2fd/ui.png' },
        { url: 'https://i.pinimg.com/736x/cf/d0/0f/cfd00ff613363792d38fb666df03331e.jpg' },
        { url: 'https://cdn.dribbble.com/userupload/3641151/file/original-d085468a47e8d5da76cdf61928f01c74.png?resize=400x0' }
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
  max-width: 900px;
  margin: 0 auto;
}

.viewport {
  overflow: hidden;
  width: 700px; /* Adjust this to match the width of your viewport */
  padding-bottom: 90px;
}

.carousel-inner {
  display: flex;
  transition: transform 0.3s ease-in-out;
}

.slide {
  flex: 0 0 auto;
  margin-right: 10px; /* Adjust as needed for spacing between slides */
  width: 200px;
  height: auto;
  background-color: white;
  margin: 0 15px;
  border-radius: 15px;
  -webkit-box-shadow: 10px 10px 15px -3px rgba(0,0,0,0.43);
    -moz-box-shadow: 10px 10px 15px -3px rgba(0,0,0,0.43);
    box-shadow: 10px 10px 15px -3px rgba(0,0,0,0.43);
}
.slide-img { border-radius: 15px; }

.previous-btn { margin-right: 40px;}
.next-btn { margin-left: 50px; }

img {
  max-width: 100%;
  height: auto;
}
</style>
