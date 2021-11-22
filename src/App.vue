<template>
  <header>
    <h2>{{ msg }}</h2>
  </header>
  <div>
    <p>My Rating: {{ myRating }}</p>
    <the-rating v-model="myRating"></the-rating>
  </div>
</template>

<script>
import TheRating from "./TheRating.vue";

export default {
  data() {
    return {
      msg: "Vue3 Bangla Tutorial",
      myRating: 4
    };
  },
  methods: {},
  components: {
    TheRating
  }
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

ul {
  margin-left: 22px;
}

body {
  font-family: sans-serif;
  line-height: 1.8;
}

header {
  background-color: #1f2c46;
  color: #41b883;
  font-size: 22px;
  padding: 22px;
}

header h2 {
  text-align: center;
}

button {
  margin: 5px;
  padding: 5px 11px;
  cursor: pointer;
}
</style>
