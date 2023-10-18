<template>
  <header>
    <div class="logo">UX Pays</div>
    <nav class="right-element">
      <router-link to="/">Home</router-link>
      <router-link to="/about">About</router-link>
      <router-link to="/contact">Contact</router-link>
    </nav>
  </header>
</template>

<style scoped>
/* Add CSS styling here */
  header { 
    display: flex; 
    justify-content: space-between; 
    width: 100%;
    }
    .logo {  align-self: flex-start; /* Align the left element to the start (left) */ }
    .right-element {   
      display: flex;
      justify-content: flex-end; /* Align the right elements to the end (right) */
    }
    nav { 
      height: 25px; 
      }
</style>