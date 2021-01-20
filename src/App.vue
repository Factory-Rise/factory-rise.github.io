<template>
  <div id="app">
    <div class="header">
      <img src="../public/assets/logo.png">
    </div>
    <div class="container">
      <ul class="select">
        <li><img src="../public/assets/home-button.png" class="btn homeBtn" v-on:click="homeBtn"></li>
        <li><img src="../public/assets/state-button.png" button class="btn stateBtn" v-on:click="stateBtn"></li>
        <li><img src="../public/assets/about-button.png" class="btn aboutBtn" v-on:click="aboutBtn"></li>
      </ul>
      <div class="dynamicPage">
        <keep-alive>
          <component v-bind:is="component"></component>
        </keep-alive>
      </div>
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
