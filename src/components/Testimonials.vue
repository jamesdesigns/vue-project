<template>
  <div class="testimonial-slider">
    <h3>Client Success Stories</h3>
    <div class="testimonial" v-for="(testimonial, index) in testimonials" :key="index" :class="{ active: index === currentIndex }">
      <div class="testimonial-content">
        <p>{{ testimonial.message }}</p>
        <p class="author">{{ testimonial.author }}</p>
      </div>
      <img :src="testimonial.profilePicture" alt="Profile Picture" class="profile-picture" />
    </div>
    <div class="slider-controls">
      <button @click="prevTestimonial" :disabled="currentIndex === 0">Previous</button>
      <button @click="nextTestimonial" :disabled="currentIndex === testimonials.length - 1">Next</button>
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
  margin-top: 15px;
  text-align: center;
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
