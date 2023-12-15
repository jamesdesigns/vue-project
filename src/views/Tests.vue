<template>
  <Header />
  <div class="about">
    <h1>Test your knowledge.</h1>
  </div>
  <Footer />
</template>

<style>

.about {
  display: flex;
  align-items: center;
  justify-content: center;
  color: #090909;
  height: 90vh;
}
</style>


<script>
import Header from "@/components/Header.vue";
import TestTwo from "@/components/TestTwo.vue";
import Footer from "@/components/Footer.vue";

export default {
  components: {
    Header,
    TestTwo,
    Footer,
  }
}
</script>
