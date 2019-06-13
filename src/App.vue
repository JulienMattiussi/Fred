<template>
  <div id="app">
    <img class="main-image" alt="Fred" src="./assets/pierre_large.jpg">
    <HelloFred msg="Welcome to Fred"/>

    <FredThink v-if="path === '/think'" :msg="message"/>
    <FredTalk v-else :msg="message"/>
  </div>
</template>

<script>
const path = window.location.pathname;
let message = "";

function getRandomIntInclusive(min, max) {
  min = Math.ceil(min);
  max = Math.floor(max);
  return Math.floor(Math.random() * (max - min + 1)) + min;
}

import HelloFred from "./components/HelloFred.vue";
import FredTalk from "./components/FredTalk.vue";
import FredThink from "./components/FredThink.vue";

export default {
  name: "app",
  data() {
    return { path, message };
  },
  created() {
    this.getDataFromAPi();
  },
  methods: {
    getDataFromAPi() {
      fetch("http://demo9993283.mockable.io/fred")
        .then(data => {
          return data.json();
        })
        .then(messages => {
          const msg = messages.msg;
          console.log(msg);
          this.message = msg[getRandomIntInclusive(0, msg.length - 1)];
        });
    }
  },
  components: {
    HelloFred,
    FredTalk,
    FredThink
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.main-image {
  width: 800px;
}
</style>
