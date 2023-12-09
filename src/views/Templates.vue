<template>
  <Header />
  <div class="templates">
    <h1>UX/UI Templates</h1>
    <TemplateGallery />
  </div>
  <Footer />
</template>

<style scoped>
h1 { color: #090909;text-align: center;font-size: 2.5rem;font-weight: bold; line-height: 1.25; padding: 50px 0 0;}
.templates {
    height: auto;
  }
  
</style>

<script>
import { TimelineLite } from 'gsap'
import Header from "@/components/Header.vue";
import TemplateGallery from "@/components/TemplateGallery.vue";
import Footer from "@/components/Footer.vue";

export default {
  components: {
    Header,
    TemplateGallery,
    Footer
  }
}
</script>
