<template>
  <Header />
  <div class="templates">
    <h1>UX/UI Templates</h1>
  </div>
  <Footer />
</template>

<style>

h1 { color: white;text-align: center;font-size: 2.5rem; line-height: 1.25;}
.templates {
  display: flex;
    align-items: center;
    justify-content: center;
    color: white;
    height: 90vh;
  }
  .template-gallery {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-template-rows: repeat(5, 1fr);
  grid-column-gap: 0px;
  grid-row-gap: 0px;
  justify-items: center;
  position: relative;
  padding-bottom:5%; 
  height: auto;
  overflow: hidden;
  width: 100%;
}
@media only screen and (max-width: 1000px) {
    .template-gallery { 
      display:flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      margin: 0 auto;
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
