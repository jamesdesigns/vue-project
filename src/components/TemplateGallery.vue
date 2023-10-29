<template>
  <div class="template-gallery">
    <div v-for="(template, index) in templates" :key="index" class="template-item">
      <img class="template-size" :src="template.imageUrl" alt="Template" />
      <div class="template-details">
        <h3>{{ template.name }}</h3>
        <p>{{ template.description }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      templates: [
        {
          name: 'UI Buttons',
          description: '$4.99',
          imageUrl: 'https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Flearnworthy.net%2Fwp-content%2Fuploads%2F2019%2F11%2FBest-iOS-Libraries-to-Make-Your-Apps-Ui-Really-Pop.png&f=1&nofb=1&ipt=3968944ceb32eee237ba1d382716d528d61bfe1d0f018e0be42f644aba2e1964&ipo=images',
        },
        {
          name: 'UI Mobile Template',
          description: '$5.99',
          imageUrl: 'https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Flearnworthy.net%2Fwp-content%2Fuploads%2F2019%2F11%2FBest-iOS-Libraries-to-Make-Your-Apps-Ui-Really-Pop.png&f=1&nofb=1&ipt=3968944ceb32eee237ba1d382716d528d61bfe1d0f018e0be42f644aba2e1964&ipo=images',
        },
        {
          name: 'UI Website Template',
          description: '$5.99',
          imageUrl: 'https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Flearnworthy.net%2Fwp-content%2Fuploads%2F2019%2F11%2FBest-iOS-Libraries-to-Make-Your-Apps-Ui-Really-Pop.png&f=1&nofb=1&ipt=3968944ceb32eee237ba1d382716d528d61bfe1d0f018e0be42f644aba2e1964&ipo=images',
        },
        {
          name: 'UX/UI Research Tempalte',
          description: '$3.99',
          imageUrl: 'https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Flearnworthy.net%2Fwp-content%2Fuploads%2F2019%2F11%2FBest-iOS-Libraries-to-Make-Your-Apps-Ui-Really-Pop.png&f=1&nofb=1&ipt=3968944ceb32eee237ba1d382716d528d61bfe1d0f018e0be42f644aba2e1964&ipo=images',
        },
        {
          name: 'UI Navigation Template',
          description: '$1.99',
          imageUrl: 'https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Flearnworthy.net%2Fwp-content%2Fuploads%2F2019%2F11%2FBest-iOS-Libraries-to-Make-Your-Apps-Ui-Really-Pop.png&f=1&nofb=1&ipt=3968944ceb32eee237ba1d382716d528d61bfe1d0f018e0be42f644aba2e1964&ipo=images',
        },
        {
          name: 'UI Dashboard Template',
          description: '$5.99',
          imageUrl: 'https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Flearnworthy.net%2Fwp-content%2Fuploads%2F2019%2F11%2FBest-iOS-Libraries-to-Make-Your-Apps-Ui-Really-Pop.png&f=1&nofb=1&ipt=3968944ceb32eee237ba1d382716d528d61bfe1d0f018e0be42f644aba2e1964&ipo=images',
        },
        {
          name: 'Ecommerce Template',
          description: '$9.99',
          imageUrl: 'https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Flearnworthy.net%2Fwp-content%2Fuploads%2F2019%2F11%2FBest-iOS-Libraries-to-Make-Your-Apps-Ui-Really-Pop.png&f=1&nofb=1&ipt=3968944ceb32eee237ba1d382716d528d61bfe1d0f018e0be42f644aba2e1964&ipo=images',
        },
        {
          name: 'Power Point Template',
          description: '$2.99',
          imageUrl: 'https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Flearnworthy.net%2Fwp-content%2Fuploads%2F2019%2F11%2FBest-iOS-Libraries-to-Make-Your-Apps-Ui-Really-Pop.png&f=1&nofb=1&ipt=3968944ceb32eee237ba1d382716d528d61bfe1d0f018e0be42f644aba2e1964&ipo=images',
        },
        {
          name: 'UI Widget Template',
          description: '$3.99',
          imageUrl: 'https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Flearnworthy.net%2Fwp-content%2Fuploads%2F2019%2F11%2FBest-iOS-Libraries-to-Make-Your-Apps-Ui-Really-Pop.png&f=1&nofb=1&ipt=3968944ceb32eee237ba1d382716d528d61bfe1d0f018e0be42f644aba2e1964&ipo=images',
        },
      ],
    };
  },
};
</script>

<style scoped>
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

.template-size { min-width: 250px; height: auto;}

.template-item {
  border: 1px solid #ccc;
  border-radius: 10px;
  padding: 10px;
  margin-bottom: 30px;
  background-color: white;
}

.template-item img {
  max-width: 300px;
  height: auto;
}

.template-details {
  text-align: center;
}
</style>
