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
      @continueClick="handleContinueClick"
    ></the-comment>
    <br />
    <hr />
    <br />

    <p>
      {{ myComment }}
    </p>

    <button @click="showNotification">Show Notification</button>

    <the-dialog heading="Are you sure" v-if="showDialog">
      <p>
        Are you really want to comment?
        <br />
        <button @click="showDialog = false">Yes</button>
        <button @click="showDialog = false">No</button>
      </p>
    </the-dialog>

    <the-notification
      v-for="(n, i) in notifications"
      :key="i"
      :text="n"
    ></the-notification>
  </div>
</template>

<script>
import TheComment from "./TheComment.vue";
import TheDialog from "./TheDialog.vue";
import TheNotification from "./TheNotification.vue";

export default {
  data() {
    return {
      msg: "Vue3 Bangla Tutorial",
      myComment: "",
      showDialog: false,
      notifications: []
    };
  },
  methods: {
    handleClick() {
      console.log("Clicked");
    },
    handleContinueClick() {
      this.showDialog = true;
    },
    showNotification() {
      this.notifications.push("You have a new notification");
      setTimeout(() => {
        this.notifications.shift();
      }, 2222);
    }
  },
  components: {
    TheComment,
    TheDialog,
    TheNotification
  }

  // beforeCreate() {
  //   console.log("befreCreate");
  // },
  // created() {
  //   console.log("created");
  // },
  // beforeMount() {
  //   console.log("beforeMount");
  // },
  // mounted() {
  //   console.log("mounted");
  // },
  // beforeUpdate() {
  //   console.log("beforeUpdate");
  // },
  // updated() {
  //   console.log("updated");
  // }
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
  color: red;
  font-size: 33px;
  border: 3px solid green;
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
