<template>
  <section class="hero">
    <div class="hero-content">
      <h1 class="large-text" ref="box">Get Hired</h1>
      <p class="intro" ref="box2">Unlock your path to a thriving career as a UX/UI Designer with our comprehensive eBook – your ultimate guide to landing that dream job!</p>
      <div class="cta-section">
        <button @click="downloadPDF">Download FREE eBook</button>
        <button class="orange-cta">Buy UX Template $9.99</button>
      </div>
    </div>
    <div class="hero-image">
      <!-- <img src="../assets/logo.svg" alt="Image of E-book" width="200" /> -->
    </div>
  </section>
</template>

<style scoped>
  body { font-family: 'Roboto', sans-serif; }
  .hero { 
    display: flex;
    flex-direction:column;
    align-items: center;
    justify-content: center;
    height: 100vh;
    width: 100%;
    color: #090909;
  }
  .hero-content { text-align: center;}
  .intro { max-width: 725px; color: #090909; font-size:1.5rem;margin-top:20px;margin-bottom: 35px;line-height: 1.3;}
  button { 
    /* padding: 20px 40px; 
    border-radius: 50px;
    background-color: #1488CC;
    color: #090909;
    font-size: 1.15rem;
    border: none;
    margin-bottom: 30px;
    cursor: pointer;
    -webkit-box-shadow: 10px 10px 15px -3px rgba(0,0,0,0.43);
    -moz-box-shadow: 10px 10px 15px -3px rgba(0,0,0,0.43);
    box-shadow: 10px 10px 15px -3px rgba(0,0,0,0.43); */
    color: #090909;
    padding: 0.7em 1.7em;
    font-size: 18px;
    border-radius: 35px;
    height: 55px;
    background: #e8e8e8;
    border: 1px solid #e8e8e8;
    transition: all .3s;
    box-shadow: 6px 6px 12px #c5c5c5, -6px -6px 12px #ffffff;
  }
  .orange-cta {
    margin-left: 20px; 
    background-color: rgb(255, 255, 255); 
    color: #090909; 
    border: 1px solid white;
  }
  .orange-cta:hover { 
    background-color: orange;
    color:black;
  }
  button:hover {
    /* -webkit-box-shadow: none;
    -moz-box-shadow: none;
    box-shadow: none;
    animation: 3s ease-in 1s;
    background-color:#ffffff;
    color: black; */
    border: 1px solid orange;
    background: white;
  }
  button:active {
  box-shadow: 4px 4px 12px #c5c5c5,
             -4px -4px 12px #ffffff;
}
  .large-text { font-size: 5rem; font-weight: bold;color:#090909;line-height: 1; }

  @media only screen and (max-width: 767px) {
    .intro { font-size: 1.25rem; }
    .orange-cta { margin-left: 0; }
    .large-text { font-size: 3rem; }
}
</style>

<script> 
import { TimelineLite } from 'gsap'
import jsPDF from 'jspdf';

export default { 
  mounted() { 
    const { box } = this.$refs
    const timeline = new TimelineLite() 
    
    timeline.to(box, 1, { y: -10, duration:.5, scale: 1.25 }) 
  },
  methods: {
    downloadPDF() {
      // Create a new instance of jsPDF
      const pdf = new jsPDF();

      // Add content to the PDF (example: a simple text)
      pdf.text('Hello, this is your PDF!', 10, 10);

      // Save the PDF as a blob
      const blob = pdf.output('blob');

      // Create a download link and trigger the download
      const link = document.createElement('a');
      link.href = URL.createObjectURL(blob);
      link.download = 'your_file_name.pdf';
      link.click();

      // Release the blob
      URL.revokeObjectURL(link.href);
    },
  }, 
} 
</script>