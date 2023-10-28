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
          imageUrl: 'template1.jpg',
        },
        {
          name: 'Template 2',
          description: 'Template 2',
          imageUrl: 'template2.jpg',
        },
        {
          name: 'Template 3',
          description: 'Template 3',
          imageUrl: 'template3.jpg',
        },
        {
          name: 'Template 4',
          description: 'Template 4',
          imageUrl: 'template1.jpg',
        },
        {
          name: 'Template 5',
          description: 'Template 5',
          imageUrl: 'template2.jpg',
        },
        {
          name: 'Template 6',
          description: 'Template 6',
          imageUrl: 'template3.jpg',
        },
        {
          name: 'Template 7',
          description: 'Template 7',
          imageUrl: 'template3.jpg',
        },
        {
          name: 'Template 8',
          description: 'Template 8',
          imageUrl: 'template1.jpg',
        },
        {
          name: 'Template 9',
          description: 'Template 9',
          imageUrl: 'template2.jpg',
        },
      ],
    };
  },
};
</script>

<style scoped>
.template-gallery {
  /* display: grid;
  grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
  gap: 20px; */
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
  padding: 10px;
  margin-bottom: 30px;
  background-color: white;
}

.template-item img {
  max-width: 100%;
  height: auto;
}

.template-details {
  text-align: center;
}
</style>
