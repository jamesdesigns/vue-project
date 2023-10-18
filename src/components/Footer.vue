<template>
  <footer>
    <div class="logo">UX Pays</div>
    <nav class="right-element">
      <router-link to="/terms">Terms</router-link>
      <router-link to="/privacy">Privacy</router-link>
      <router-link to="/contact">Contact</router-link>
    </nav>
  </footer>
</template>

<style scoped>
/* Add your CSS styling here */
footer { 
  display: flex; 
  justify-content: space-between; 
  padding-bottom: 30px 0;
}
.logo {
  align-self: flex-start; /* Align the left element to the start (left) */
}
.right-element {
  display: flex;
  justify-content: flex-end; /* Align the right elements to the end (right) */
}
</style>
