<template>
  <div ref="content" class="lazy-content">
    <!-- Your lazy-loaded content goes here -->
    <h2 v-if="showTitle" class="fade-in">Welcome to My Vue.js Landing Page</h2>
    <p v-if="showParagraph" class="fade-in">Scroll down to explore more...</p>
  </div>
</template>

<script>
import { gsap } from 'gsap';

export default {
  data() {
    return {
      showTitle: false,
      showParagraph: false,
    };
  },
  methods: {
    handleScroll() {
      const rect = this.$refs.content.getBoundingClientRect();
      const windowHeight = window.innerHeight;

      // Check if the element is in the viewport
      if (rect.top < windowHeight * 0.75 && rect.bottom >= 0) {
        this.showTitle = true;
        this.showParagraph = true;

        // GSAP animation
        gsap.from(this.$refs.content, { opacity: 0, duration: 1 });
      }
    },
  },
  mounted() {
    // Attach scroll event listener
    window.addEventListener('scroll', this.handleScroll);

    // Initial check
    this.handleScroll();
  },
  beforeDestroy() {
    // Remove scroll event listener to avoid memory leaks
    window.removeEventListener('scroll', this.handleScroll);
  },
};
</script>

<style scoped>
.lazy-content { height: 600px; color: white; }
.fade-in {
  color: white;
  opacity: 1;
}
</style>
