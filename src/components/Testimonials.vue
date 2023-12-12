<template>
  <div class="testimonial-slider">
    <div class="testimonial" v-for="(testimonial, index) in testimonials" :key="index" :class="{ active: index === currentIndex }">
      <p>{{ testimonial.message }}</p>
      <p class="author">{{ testimonial.author }}</p>
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
        },
        {
          message: "Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.",
          author: "Jane Smith",
        },
        {
          message: "Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.",
          author: "Alice Johnson",
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
.testimonial-slider {
  position: relative;
  max-width: 600px;
  margin: 0 auto;
}

.testimonial {
  display: none;
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 5px;
  background-color: #f9f9f9;
}

.testimonial.active {
  display: block;
}

.author {
  margin-top: 10px;
  font-style: italic;
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
