<template>
  <header>
    <h2>{{ msg }}</h2>
  </header>

  <div class="container">
    <the-comment
      v-model="myComment"
      buttonText="Continue"
      placeholder="Enter Your comment.."
      @click="handleClick"
    ></the-comment>
    <br />
    <hr />
    <br />

    <p>
      {{ myComment }}
    </p>
  </div>
</template>

<script>
import TheComment from "./TheComment.vue";

export default {
  data() {
    return {
      msg: "Vue3 Bangla Tutorial",
      myComment: ""
    };
  },
  methods: {
    handleClick() {
      console.log("Clicked");
    }
  },
  components: {
    TheComment
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

.container {
  padding: 22px;
}

button {
  margin: 5px;
  padding: 5px 11px;
  cursor: pointer;
}

.shadowed {
  box-shadow: 0 0 3px 2px #111;
}
</style>
