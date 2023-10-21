<template>
  <div  class="contact">
  <Header />
  <div>
    <h1>Hi! It's nice to meet you.</h1>
  </div>
  <Footer />
</div>
</template>

<style>
/* @media (min-width: 1024px) { */
  .contact {
    min-height: 100vh;
    /* display: flex;
    align-items: center;
    justify-content: center; */
    color: white;
  }
/* } */
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
