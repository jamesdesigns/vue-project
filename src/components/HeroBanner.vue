<template>
  <section class="hero">
    <div class="hero-content">
      <h1 class="large-text">Get Hired</h1>
      <p class="intro">Unlock your path to a thriving career as a UX/UI Designer with our comprehensive Ebook – your ultimate guide to landing that dream job!</p>
      <button>Download E-book</button>
    </div>
    <div class="hero-image">
      <!-- <img src="../assets/logo.svg" alt="Image of E-book" width="200" /> -->
    </div>
  </section>
</template>

<style scoped>
/* Add your CSS styling here */
  .hero { 
    display: flex;
    flex-direction:column;
    align-items: center;
    justify-content: center;
    height: 85vh;
    width: 100%;
  }
  .hero-content { text-align: center;}
  .intro { max-width: 625px; color: white; font-size:1.5rem;margin-bottom: 30px;line-height: 1.3;}
  button { 
    padding: 20px 50px; 
    border-radius: 50px;
    background-color: #061161;
    color: white;
    font-size: 1.5rem;
    border: none;
    margin-bottom: 30px;
    cursor: pointer;
  }
  .large-text { font-size: 5rem; font-weight: bold;color:white;line-height: 1;margin-bottom: 30px; }

</style>