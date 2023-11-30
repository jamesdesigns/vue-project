<template>
  <div>
    <Header />
    <HeroBanner />
    <ImageCarousel />
    <Test />
    <Footer />
  </div>
</template>

<script>
import { TimelineLite } from 'gsap'


import Header from "@/components/Header.vue";
import HeroBanner from "@/components/HeroBanner.vue";
import ImageCarousel from "@/components/ImageCarousel.vue";
import Test from '@/components/Test.vue'; // Adjust the path accordingly
import Footer from "@/components/Footer.vue";


export default {
  components: {
    Header,
    HeroBanner,
    ImageCarousel,
    Test,
    Footer
  },
}
</script>

<style scoped>
body {
  font-family: 'Roboto', sans-serif; /* Use the font name specified in Google Fonts */
}

/* Add your CSS styling here */

</style>
