<template>
  <div class="think">
    <img class="think-image" alt="Fred talk" src="../assets/bulle_pensée.png">
    <h1 class="think-text">{{ msg }}</h1>
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
.think {
  position: absolute;
  margin-left: auto;
  margin-right: auto;
  left: 0;
  right: 0;
  top: 60px;
  width: 800px;
  height: 300px;
}
.think-image {
  position: absolute;
  left: 0px;
  width: 350px;
  height: 300px;
}

.think-text {
  position: absolute;
  left: 0px;
  top: 50px;
  width: 300px;
}
</style>
