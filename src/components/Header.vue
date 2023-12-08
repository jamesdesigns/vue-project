<template>
  <header>
    <router-link to="/" class="logo">UX Pays &nbsp;&nbsp;<span class="small-tagline">Learn more. Earn more.</span></router-link>
    <nav class="right-element">
      <router-link to="/tutorials" class="btn nav-link-1">Tutorials</router-link>
      <router-link to="/templates" class="btn nav-link-1">Templates</router-link>
      <router-link to="/tests" class="btn nav-link-1">Tests</router-link>
      <router-link to="/about" class="btn nav-link-2">About Us</router-link>
      <router-link to="/contact" class="btn nav-link-3">Contact Us</router-link>
    </nav>
  </header>
</template>

<style scoped>
/* Add CSS styling here */
  header { 
    display: flex; 
    justify-content: space-between; 
    width: 100%;
    color: #090909;
    padding-top: 4px;
    }
    .logo {  align-self: flex-start; /* Align the left element to the start (left) */ 
    font-size: 1.25rem;
    font-weight: Bold;
    color: #090909;
    }
    .small-tagline { font-size: .9rem; }
    .btn {
      color: #090909;
    padding: 0.5em 1.7em;
    font-size: 18px;
    height: 45px;
 
    }
    .btn:hover { 
      /* background-color: white; 
      opacity: 1; 
      border-radius: 35px;  */
      border: 1px solid white;
    background: white;
    border-radius: 35px;
    height: 45px;
    background: #e8e8e8;
    border: 1px solid #e8e8e8;
    /* transition: all .3s; */
    box-shadow: 6px 6px 12px #c5c5c5, -6px -6px 12px #ffffff;
    
    }
    .right-element {   
      display: flex;
      justify-content: flex-end; /* Align the right elements to the end (right) */
    }
    .right-element .nav-link-1,
    .right-element .nav-link-2 { margin: 5px; color: #090909; font-size: 1.05rem; font-weight:400; }
    .right-element .nav-link-3 { margin: 5px; color: #090909; font-size: 1.05rem; font-weight: 400; }

    .nav-link-1:hover,
    .nav-link-2:hover,
    .nav-link-3:hover {
      /* color: #2f63ba; */
      color: #090909;
    }

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