<template>
  <header>
    <div class="logo">UX Pays</div>
    <nav class="right-element">
      <router-link to="/" class="nav-link-1">Home</router-link>
      <router-link to="/about" class="nav-link-2">About</router-link>
      <router-link to="/contact" class="nav-link-3">Contact</router-link>
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
    .right-element .nav-link-1,
    .right-element .nav-link-2 { margin: 0 25px;}
    .right-element .nav-link-3 { margin: 0 0 0 25px;}
    nav { 
      height: 25px; 
      }
</style>