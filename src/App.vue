<template>
  <div id="app">
    <div class="header">
      <img src="./assets/logo.png">
    </div>

    <div class="dynamicPage">
      <component v-bind:is="currentPage" class="currentPage"></component>
    </div>
  </div>
</template>

<script>
  export default {
    name: '.app',
    data: {
      currentPage: "home",
      pages: ["home", "state", "about"]
    },
    components: {}
  }
</script>
