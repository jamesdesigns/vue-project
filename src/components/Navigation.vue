<template>
  <nav>
    <button @click="toggleMenu" class="mobile-menu-button">
      <i class="fa fa-bars"></i> <!-- You can use an icon library like FontAwesome for the menu icon -->
    </button>
    <ul :class="{'show-menu': showMenu}">
      <!-- Your navigation links go here -->
    </ul>
  </nav>
</template>

<script>
export default {
  data() {
    return {
      showMenu: false
    };
  },
  methods: {
    toggleMenu() {
      this.showMenu = !this.showMenu;
    }
  }
}
</script>

<style scoped>
/* Add your CSS styling here */
.mobile-menu-button {
  display: block; /* Show the button on all screen sizes */
  // Add styles for the button, e.g., background color, icon size, etc.
}

ul {
  list-style-type: none;
  padding: 0;
}

ul.show-menu {
  display: flex;
  flex-direction: column;
  align-items: center; /* Center the items vertically */
  /* Add other styles for the open menu */
}

/* Add more styles for your navigation links as needed */

</style>
