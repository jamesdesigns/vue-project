<template>
  <Header />
  <div class="templates">
    <h1>UX/UI Templates</h1>
  </div>
  <Footer />
</template>

<style>

h1 { color: white;text-align: center;font-size: 3.5rem; line-height: 1.25;}
.templates {
  display: flex;
    align-items: center;
    justify-content: center;
    color: white;
    height: 90vh;
  }
</style>

<script>
import Header from "@/components/Header.vue";
import Footer from "@/components/Footer.vue";

export default {
  components: {
    Header,
    Footer
  }
}
</script>
