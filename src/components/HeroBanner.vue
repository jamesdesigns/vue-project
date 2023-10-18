<template>
  <section class="hero">
    <div class="hero-content">
      <h1 class="large-text">Get Hired</h1>
      <button>Download E-book</button>
    </div>
    <div class="hero-image">
      <img src="../assets/logo.svg" alt="Image of E-book" width="200" />
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
    height: 70vh;
    width: 100%;
  }
  .hero-content { text-align: center;}
  button { 
    padding: 20px 50px; 
    border-radius: 50px;
    background-color: #0099ff;
    color: white;
    font-size: 1.5rem;
    border: none;
    margin-bottom: 30px;
    cursor: pointer;
  }
  .large-text { font-size: 4rem; font-weight: bold; }

</style>