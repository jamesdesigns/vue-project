<template>
  <section class="hero">
    <div class="hero-content">
      <h1 class="large-text" ref="box">Get Hired</h1>
      <p class="intro" ref="box2">Unlock your path to a thriving career as a UX/UI Designer with our comprehensive eBook – your ultimate guide to landing that dream job!</p>
      
      <div class="cta-section">
        <button>Download FREE eBook</button>
        <button class="orange-cta">Buy UX Template $9.99</button>
      </div>
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
  .intro { max-width: 625px; color: white; font-size:1.5rem;margin-top:30px;margin-bottom: 35px;line-height: 1.3;}
  button { 
    padding: 20px 40px; 
    border-radius: 50px;
    /* background-color: #061161; */
    background-color: #1488CC;
    color: white;
    font-size: 1.15rem;
    border: none;
    margin-bottom: 30px;
    cursor: pointer;
    -webkit-box-shadow: 10px 10px 15px -3px rgba(0,0,0,0.43);
    -moz-box-shadow: 10px 10px 15px -3px rgba(0,0,0,0.43);
    box-shadow: 10px 10px 15px -3px rgba(0,0,0,0.43);
  }
  .orange-cta {margin-left: 30px; background-color: orange; color: black;}
  .orange-cta:hover { background-color: rgb(255, 255, 255);}
  button:hover {
    -webkit-box-shadow: none;
    -moz-box-shadow: none;
    box-shadow: none;
    animation: 3s ease-in 1s;
    background-color:#ffffff;
    color: black;
  }
  .large-text { font-size: 5rem; font-weight: bold;color:white;line-height: 1; }
  @media only screen and (max-width: 767px) {
    .orange-cta { margin-left: 0; }
}
</style>

<script> 
import { TimelineLite } from 'gsap'
export default { 
  mounted() { 
    const { box } = this.$refs
    const timeline = new TimelineLite() 
    
    timeline.to(box, 1, { y: -20, duration:1, scale: 1.25 }) 
  } 
} 
</script>