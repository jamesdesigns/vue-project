<template>
  <Header />
  <div class="tutorials">
    <h1>UX/UI Tutorials</h1>
  </div>
  <Footer />
</template>

<style>
@media (min-width: 1024px) {
  /* .tutorials {
    min-height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    color: white;
  } */
}
h1 { color: white;text-align: center;font-size: 3.5rem}
.tutorials {
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
