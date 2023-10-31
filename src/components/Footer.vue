<template>
  <footer>
    <div class="logo">Learn more. Get Paid more.</div>
    <nav class="footer right-element">
      <router-link to="/terms" class="footer-nav-link-1">Terms</router-link>
      <router-link to="/privacy"  class="footer-nav-link-2">Privacy</router-link>
    </nav>
  </footer>
</template>

<style scoped>
/* Add your CSS styling here */
footer { 
  display: flex; 
  justify-content: space-between; 
  padding-bottom: 30px 0;
  margin-right: 30px;
}
.logo {
  align-self: flex-start; /* Align the left element to the start (left) */
  color: white;
}

.right-element {
  display: flex;
  justify-content: flex-end; /* Align the right elements to the end (right) */
}
.right-element .footer-nav-link-1{ margin: 0 20px;color:white;}
.right-element .footer-nav-link-2 { margin: 0 0 0 5px;color:white;}
</style>
