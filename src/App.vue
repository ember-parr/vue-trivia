<template>
  <div id="app">
    <img alt="Trivia Header" src="./assets/hero_image.jpg" class="hero-image" />
    <trivia-game />
  </div>
</template>

<script>
import TriviaGame from "./components/TriviaGame.vue";

export default {
  name: "App",
  components: {
    TriviaGame
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 10px;
}
.hero-image {
  width: 100%;
  height: auto;
  min-width: 300px;
}
</style>
