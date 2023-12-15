<template>
  <div class="testimonial-slider">
    <h3>Our Users Success Stories</h3>
    <div class="testimonial" v-for="(testimonial, index) in testimonials" :key="index" :class="{ active: index === currentIndex }">
      <div class="testimonial-content">
        <p>{{ testimonial.message }}</p>
        <p class="author">{{ testimonial.author }}</p>
      </div>
      <img :src="testimonial.profilePicture" alt="Profile Picture" class="profile-picture" />
    </div>
    <div class="slider-controls">
      <div class="arrow left player__btn player__btn--small" id="previous" @click="prevImage">
        <button @click="prevTestimonial" :disabled="currentIndex === 0"><i class="fas fa-arrow-left"></i></button>
      </div>
      <!-- <button @click="prevTestimonial" :disabled="currentIndex === 0">Previous</button>
      <button @click="nextTestimonial" :disabled="currentIndex === testimonials.length - 1">Next</button> -->
      <div class="arrow right player__btn player__btn--small" id="previous" @click="nextImage">
        <button @click="nextTestimonial" :disabled="currentIndex === testimonials.length - 1"><i class="fas fa-arrow-left"></i></button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      currentIndex: 0,
      testimonials: [
        {
          message: "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
          author: "John Doe",
          profilePicture: "https://placehold.co/200x200",
        },
        {
          message: "Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.",
          author: "Jane Smith",
          profilePicture: "https://placehold.co/200x200",
        },
        {
          message: "Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.",
          author: "Alice Johnson",
          profilePicture: "https://placehold.co/200x200",
        },
      ],
    };
  },
  methods: {
    nextTestimonial() {
      this.currentIndex = (this.currentIndex + 1) % this.testimonials.length;
    },
    prevTestimonial() {
      this.currentIndex = (this.currentIndex - 1 + this.testimonials.length) % this.testimonials.length;
    },
  },
};
</script>

<style scoped>
h3 { text-align: center; font-size: 2rem; font-weight: bold; margin-bottom: 30px; }
.testimonial-slider {
  position: relative;
  max-width: 850px;
  margin: 0 auto;
  height: 70vh;
}

.player__btn {
  cursor: pointer;
  border-radius: 50%;
  width: 50px;
  /* display: flex;
  flex-direction: row;
  justify-content: center; */
  align-items: center;
  box-shadow: -8px -8px 20px 0px #fff9, -6px -6px 6px 0px #fff9,
    8px 8px 20px #0001, 5px 5px 6px 0px #0001;
  color: gray;
}

.player__btn:active {
  box-shadow: inset -8px -8px 20px #fff9, inset -5px -5px 6px #fff9,
    inset 8px 8px 20px #0003, inset 5px 5px 6px #0001;
}

.player__btn--small {
  min-width: 50px;
  min-height: 50px;
  margin: 0 10px;
}


.testimonial {
  display: none;
  padding: 60px;
  border: 1px solid #ccc;
  border-radius: 15px;
  background-color: #f9f9f9;
  position: relative;
}

.testimonial.active {
  display: block;
}

.testimonial-content {
  margin-bottom: 15px;
  max-width: 550px;
  margin-left: 175px;
}

.author {
  margin-top: 10px;
  font-style: italic;
}

.profile-picture {
  width: 150px;
  height: 150px;
  border-radius: 50%;
  object-fit: cover;
  position: absolute;
  top: 35px;
  left: 35px;
}

.slider-controls {
  display: flex;
  flex-direction: row;
  justify-content: center;
  width: 200px;
  margin-top: 15px;
  text-align: center;
  margin: 3% auto 0;
}

button {
  padding: 10px;
  margin: 0 5px;
  cursor: pointer;
  border: none;
  background-color: #3498db;
  color: #fff;
}

button:disabled {
  background-color: #ccc;
  cursor: not-allowed;
}
</style>
