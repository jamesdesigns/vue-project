<template>
  <div>
    <Header />
    <HeroBanner />
    <ImageCarousel />
    <TestTwo />
    <testimonials />
    <Footer />
  </div>
</template>

<script>
import { TimelineLite } from 'gsap'


import Header from "@/components/Header.vue";
import HeroBanner from "@/components/HeroBanner.vue";
import ImageCarousel from "@/components/ImageCarousel.vue";
import TestTwo from '@/components/TestTwo.vue';
import Testimonials from '@/components/Testimonials.vue';
import Footer from "@/components/Footer.vue";


export default {
  components: {
    Header,
    HeroBanner,
    ImageCarousel,
    TestTwo,
    Testimonials,
    Footer,
  },
}
</script>

<style scoped>
body {
  font-family: 'Roboto', sans-serif; /* Use the font name specified in Google Fonts */
}

/* Add your CSS styling here */

</style>
