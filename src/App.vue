<template>
  <header>
    <h2>{{ msg }}</h2>
  </header>

  <div class="container">
    <h1>New User Registration</h1>
    <label>Full Name</label> <br />
    <input
      type="text"
      placeholder="Enter your Full Name"
      v-model="formData.fullName"
    />
    <br />

    <label>About You</label> <br />
    <textarea
      v-model="formData.aboutYou"
      placeholder="Write something about you..."
    ></textarea>

    <br />
    <label>Gender</label> <br />

    <label>
      <input type="radio" name="gender" value="M" v-model="formData.gender" />
      Male
    </label>
    <label>
      <input
        type="radio"
        name="gender"
        class="ml-2"
        checked="checked"
        value="F"
        v-model="formData.gender"
      />
      Female
    </label>
    <label>
      <input
        type="radio"
        name="gender"
        class="ml-2"
        value="O"
        v-model="formData.gender"
      />
      Other
    </label>

    <br />
    <br />
    <label>Language</label>
    <br />
    <select v-model="formData.language">
      <option value="">--Select One--</option>
      <option value="B">Bangla</option>
      <option value="E">English</option>
    </select>

    <br />
    <br />

    <label>Skills</label>
    <br />
    <select multiple v-model="formData.skils">
      <option>HTML</option>
      <option>CSS</option>
      <option>JavaScript</option>
      <option>Python</option>
      <option>Swift</option>
    </select>

    <br />
    <br />

    <hr />

    <div v-for="(value, key) in formData" :key="key">
      <strong>{{ key }}: </strong> {{ value }}
    </div>
  </div>
</template>

<script>
// import TheComment from "./TheComment.vue";

export default {
  data() {
    return {
      msg: "Vue3 Bangla Tutorial",
      name: "",
      formData: {
        fullName: "Md. ",
        aboutYou: "",
        gender: "O",
        language: "",
        skils: []
      }
    };
  },
  created() {
    // console.dir(this.$refs.commentInput);
  },
  mounted() {
    // console.dir(this.$refs.commentInput);
  },
  methods: {},
  components: {
    // TheComment
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

.tab {
}

.tab__menu {
  display: flex;
}

.tab__menu-item {
  padding: 6px 15px;
  background-color: #dbdbdb;
  cursor: pointer;
}

.tab__menu-item--active {
  color: #fff;
  background-color: rgb(27, 104, 192);
}

input {
  padding: 5px 11px;
  margin-bottom: 11px;
}

textarea {
  padding: 5px 11px;
  margin-bottom: 11px;
  width: 100%;
}

.ml-2 {
  margin-left: 11px;
}
</style>
