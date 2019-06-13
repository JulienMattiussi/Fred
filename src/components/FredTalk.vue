<template>
  <div class="talk">
    <img class="talk-image" alt="Fred talk" src="../assets/bulle_parole.png">
    <h1 class="talk-text">{{ msg }}</h1>
  </div>
</template>

<script>
export default {
  name: "FredTalk",
  props: {
    msg: String
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.talk {
  position: absolute;
  margin-left: auto;
  margin-right: auto;
  left: 0;
  right: 0;
  top: 60px;
  width: 800px;
  height: 300px;
}
.talk-image {
  position: absolute;
  left: 0px;
  transform: scaleX(-1);
  width: 350px;
}

.talk-text {
  position: absolute;
  left: 0px;
  top: 60px;
  width: 300px;
}
</style>
