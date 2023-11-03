<template>
  <header>
    <router-link to="/" class="logo">UX Pays &nbsp;&nbsp;<span class="small-tagline">Learn more. Earn more.</span></router-link>
    <nav class="right-element">
      <router-link to="/tutorials" class="btn nav-link-1">Tutorials</router-link>
      <router-link to="/templates" class="btn nav-link-1">Templates</router-link>
      <router-link to="/about" class="btn nav-link-2">About</router-link>
      <router-link to="/contact" class="btn nav-link-3">Contact</router-link>
    </nav>
  </header>
</template>

<style scoped>
/* Add CSS styling here */
  header { 
    display: flex; 
    justify-content: space-between; 
    width: 100%;
    color: white;
    padding-top: 4px;
    }
    .logo {  align-self: flex-start; /* Align the left element to the start (left) */ 
    font-size: 1.25rem;
    font-weight: bold;
    color: white;
    }
    .small-tagline { font-size: .9rem; }
    .btn {
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 20px;
 
    }
    .right-element {   
      display: flex;
      justify-content: flex-end; /* Align the right elements to the end (right) */
    }
    .right-element .nav-link-1,
    .right-element .nav-link-2 { margin: 5px; color: white; font-size: 1.05rem; font-weight: 600; }
    .right-element .nav-link-3 { margin: 5px; color: white; font-size: 1.05rem; font-weight: 600; }
    nav { 
      height: 25px;
      }

      @media only screen and (max-width: 767px) {
        .right-element { 
          display: none; /* changes this nav to a hamburger icon */
          flex-direction: column; 
          height: 100%; }
    }
</style>