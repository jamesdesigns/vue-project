<template>
  <div>
    <Header />
    <HeroBanner />
    <ImageCarousel />
    <LazyLoadedContent />
    <Footer />
  </div>
</template>

<script>
import { TimelineLite } from 'gsap'

import Header from "@/components/Header.vue";
import HeroBanner from "@/components/HeroBanner.vue";
import ImageCarousel from "@/components/ImageCarousel.vue";
import LazyLoadedContent from '@/components/LazyLoadedContent.vue';

import Footer from "@/components/Footer.vue";

export default {
  components: {
    Header,
    HeroBanner,
    ImageCarousel,
    LazyLoadedContent,
    Footer
  }
}
</script>

<style scoped>
body {
  font-family: 'Roboto', sans-serif; /* Use the font name specified in Google Fonts */
}

/* Add your CSS styling here */

</style>
