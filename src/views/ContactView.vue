<template>
  <Header />
  <div   class="contact">
    <h1>Hi! It's nice to meet you.</h1>
  </div>
  <Footer />

</template>

<style>
  .contact {
    display: flex;
    align-items: center;
    justify-content: center;
    color: #090909;
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
