<template>
  <div id="app">
    <div class="header">
      <img src="../public/assets/logo.png">
    </div>
    <div class="container">
      <div class="select">
        <img src="../public/assets/home-button.png" class="btn homeBtn" v-on:click="homeBtn">
        <img src="../public/assets/state-button.png" button class="btn stateBtn" v-on:click="stateBtn">
        <img src="../public/assets/about-button.png" class="btn aboutBtn" v-on:click="aboutBtn">
      </div>
      <div class="dynamicPage">
        <keep-alive>
          <component v-bind:is="component"></component>
        </keep-alive>
      </div>
    </div>
    <div class="footer">
      
    </div>
  </div>
</template>

<style>
  @import './main.css';
</style>

<script>
  import Home from './components/Home.vue';
  import About from './components/About.vue';
  import State from './components/State.vue';

  export default {
    name: 'App',
    components: { Home, About, State },
    data() {
      return { component: Home }
    },
    methods: {
      homeBtn() {
        this.component = Home;
      },
      stateBtn() {
        this.component = State;
      },
      aboutBtn() {
        this.component = About;
      },
    }
  }
</script>
