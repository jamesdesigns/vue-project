<template>
  <Header />
  <div   class="contact">
    <h1>Connect with Us!</h1>
    <p>We're here to assist you. Whether you have questions, feedback, or just want to say hello, feel free to reach out. Your thoughts matter to us, and we look forward to hearing from you. Use the form below, and we'll get back to you as soon as possible. Thank you for being a part of our community!</p>
    <br>
    <br>
    <Contact />
  </div>
  <Footer />

</template>

<style>
  .contact {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    color: #090909;
    height: 90vh;
  }

  h1 {
    font-size: 2.5rem;
    font-weight: bold;
    line-height: 1.25;
    padding: 50px 0 0;
    margin-bottom: 20px;
  }
  p { max-width: 750px; }
</style>

<script>
import Header from "@/components/Header.vue";
import Contact from "@/components/Contact.vue";
import Footer from "@/components/Footer.vue";

export default {
  components: {
    Header,
    Contact,
    Footer
  }
}
</script>
