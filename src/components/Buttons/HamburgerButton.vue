<template>
    <button v-if="showHamburger" class="text-white" @click="emitToggleSidebar">
      <i class="bi bi-list"></i>
    </button>
  </template>
  
  <script>
  export default {
    methods: {
      emitToggleSidebar() {
        this.$emit('toggle-sidebar'); // Emit the event
      },
    },
    computed: {
      showHamburger() {
        const routesWithButton = ['HomePage', 'RestaurantPage'];
        return routesWithButton.includes(this.$route.name);
      },
    },
  };
  </script>
  

<style lang="scss" scoped>
button {
    background: none;
    border: none;
    color: pointer;
    padding: 0;

    i {
        font-size: 1.4rem;
    }
}
</style>