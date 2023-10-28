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
.mobile-menu-button {
  display: block; /* Show the button on all screen sizes */
}

ul {
  list-style-type: none;
  padding: 0;
}

ul.show-menu {
  display: flex;
  flex-direction: column;
  align-items: center; 
}

</style>
