<template>
  <Header />
  <div class="templates">
    <h1>UX/UI Templates</h1>
    <TemplateGallery />
  </div>
  <Footer />
</template>

<style>
h1 { color: white;text-align: center;font-size: 2.5rem; line-height: 1.25; padding: 50px 0 30px;}
.templates {
    height: auto;
  }
  
</style>

<script>
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
