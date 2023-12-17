<template>
  <div>
    <h1>Improve your design process.</h1>
    <p style="text-align: center;">Dive into seamless UX/UI with our custom templates!</p>
    <div class="carousel-container">
      <div class="carousel">
          <div class="arrow left player__btn player__btn--small" id="previous" @click="prevImage">
            <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
              <path stroke-linecap="round" stroke-linejoin="round" d="M15.75 19.5L8.25 12l7.5-7.5" />
            </svg>
          </div>
        <div class="image-wrapper carousel-card">
          <img  :src="images[currentIndex]" alt="Carousel Image" />
        </div>
          <div class="arrow right player__btn player__btn--small" id="previous" @click="nextImage">
            <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
              <path stroke-linecap="round" stroke-linejoin="round" d="M8.25 4.5l7.5 7.5-7.5 7.5" />
            </svg>
        </div>
      </div>
    </div>
</div>
</template>

<script>
export default {
  data() {
    return {
      currentIndex: 0,
      images: [
        'https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fos-system.com%2Fblog%2Fwp-content%2Fuploads%2F2020%2F12%2Fdesign-with-rounded-corners.jpg&f=1&nofb=1&ipt=e588e066cdc645655614842e0a2c00ee46a01ad0e36853684932d2a359e93542&ipo=images',
        'https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fblog.clicky.com%2Fwp-content%2Fuploads%2F2020%2F08%2F1-2.jpg&f=1&nofb=1&ipt=61f457706eb2512cc8c2b1940d60e74d5d2fafc4bcbad7161b03a029474054f8&ipo=images',
        'https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fgillde.com%2Fwp-content%2Fuploads%2F2019%2F08%2FUI-Design-30-6.jpg&f=1&nofb=1&ipt=c80687e28e997317804a05796663fb23695910b457b04a36e6208982a55774c8&ipo=images',
        'https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fi.pinimg.com%2Foriginals%2F6d%2F53%2F01%2F6d5301a6b6b41c5dc9fa8838b53a1921.png&f=1&nofb=1&ipt=3aae3624512e6f935024f2e09b765103e5fa6a56a41c8c324a944b315ca581f8&ipo=images',
        'https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fbashooka.com%2Fwp-content%2Fuploads%2F2017%2F09%2Fdashboard-ui-design-2017-5.jpg&f=1&nofb=1&ipt=5392974706f2df1ceaaaddea6cfd525092e587ca72a228a7f7792e2c4866be9a&ipo=images',
      ],
    };
  },
  methods: {
    nextImage() {
      this.currentIndex = (this.currentIndex + 1) % this.images.length;
    },
    prevImage() {
      this.currentIndex = (this.currentIndex - 1 + this.images.length) % this.images.length;
    },
  },
};
</script>

<style scoped>
h1 { font-size: 3rem; font-weight: bold; color: #242424; text-align: center;line-height: 1; margin-bottom: 30px;}
p { font-size: 1.5rem; color: #090909; text-align: center;}


.player__btn {
  cursor: pointer;
  border-radius: 50%;
  display: flex;
  justify-content: center;
  align-items: center;
  box-shadow: -8px -8px 20px 0px #fff9, -6px -6px 6px 0px #fff9,
    8px 8px 20px #0001, 5px 5px 6px 0px #0001;
  color: gray;
}

.player__btn:active {
  box-shadow: inset -8px -8px 20px #fff9, inset -5px -5px 6px #fff9,
    inset 8px 8px 20px #0003, inset 5px 5px 6px #0001;
}

.player__btn--small {
  min-width: 50px;
  min-height: 50px;
}


.carousel-container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 80vh;
}

.carousel {
  position: relative;
  max-width: 600px;
  margin: 0 auto;
}

.image-wrapper {
  overflow: hidden;
  border-radius: 8px;
}

img {
  width: 100%;
  height: auto;
  display: block;
  align-items: center;
  background-color: #e8e8e8;
  box-shadow: 
    12px 12px 16px 0 rgba(0, 0, 0, 0.25),
    -8px -8px 12px 0 rgba(255, 255, 255, 0.3);
  border-radius: 10px;
  display: flex;
  justify-content: center;
  margin-right: 4rem;

}

.carousel-card {
  -webkit-box-shadow: -5px 11px 59px -10px rgba(0,0,0,0.75);
  -moz-box-shadow: -5px 11px 59px -10px rgba(0,0,0,0.75);
  box-shadow: -5px 11px 59px -10px rgba(0,0,0,0.75);
}

.sm-right-arrow { width: 50px; border-radius: 50px; }
.sm-left-arrow { width: 50px; rotate: 180deg;border-radius: 50px;}


.arrow {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  font-size: 24px;
  color: #090909;
  background-color: transparent;
  border: none;
  border-radius:50px;
  padding: 10px;
  cursor: pointer;
  outline: none;
  transition: background-color 0.3s;
}

.arrow:hover {
  background-color: transparent;
}

.left {
  left: -100px;
}

.right {
  right: -100px;
}

@media only screen and (max-width: 768px) {
  h1 { margin-bottom: 30px;}
  }

  p {
    font-size: 1.25rem;
    line-height: 1.3;
  }
</style>
