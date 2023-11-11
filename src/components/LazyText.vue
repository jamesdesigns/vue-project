<template>
  <div ref="lazyComponent" class="lazy-component">
    <h1 v-if="isVisible" class="fade-in">Lazy Loaded Heading</h1>
    <p v-if="isVisible" class="fade-in">Lazy Loaded Paragraph</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isVisible: false,
    };
  },
  mounted() {
    this.observeElement();
  },
  methods: {
    observeElement() {
      const options = {
        rootMargin: '0px', // Adjust this margin as needed
        threshold: 0.5, // Adjust this threshold as needed (0.5 means 50% of the element must be visible)
      };

      const observer = new IntersectionObserver(this.handleIntersection, options);
      observer.observe(this.$refs.lazyComponent);
    },
    handleIntersection(entries) {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          this.isVisible = true;
          entry.target.classList.remove('fade-in'); // Reset the fade-in animation for re-triggering
        } else {
          this.isVisible = false;
        }
      });
    },
  },
};
</script>

<style scoped>
.fade-in {
  opacity: 0;
  transition: opacity 1s ease-in-out; /* Adjust the duration and easing function as needed */
}

.lazy-component {  height: 500px;}

.lazy-component .fade-in {
  opacity: 1;
  color: white;
}
</style>
