<template>
  <section class="hero">
    <div class="hero-content">
      <h1 class="large-text">Get Hired</h1>
      <p class="intro">Unlock your path to a thriving career as a UX/UI Designer with our comprehensive eBook – your ultimate guide to landing that dream job!</p>
      <button>Download eBook</button>
    </div>
    <div class="hero-image">
      <!-- <img src="../assets/logo.svg" alt="Image of E-book" width="200" /> -->
    </div>
  </section>
</template>

<style scoped>
/* Add your CSS styling here */
body {
  font-family: 'Roboto', sans-serif; /* Use the font name specified in Google Fonts */
}

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
    -webkit-box-shadow: 10px 10px 15px -3px rgba(0,0,0,0.43);
    -moz-box-shadow: 10px 10px 15px -3px rgba(0,0,0,0.43);
    box-shadow: 10px 10px 15px -3px rgba(0,0,0,0.43);
  }
  button:hover {
    -webkit-box-shadow: none;
    -moz-box-shadow: none;
    box-shadow: none;
    animation: 3s ease-in 1s;
    background-color:#000428;
  }
  .large-text { font-size: 5rem; font-weight: bold;color:white;line-height: 1;margin-bottom: 30px; }

</style>