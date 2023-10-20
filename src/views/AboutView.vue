<template>
  <Header />
  <div class="about">
    <h1>Learn how you can benefit from UX Guidelines and Template.</h1>
  </div>
  <Footer />
</template>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    color: white;
  }
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
