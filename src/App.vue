<template>
  <header>
    <h2>{{ msg }}</h2>
  </header>

  <div class="container">
    <div class="tab">
      <div class="tab__menu">
        <div
          v-for="tab in tabs"
          :key="tab"
          class="tab__menu-item"
          :class="{ 'tab__menu-item--active': activeTab === tab }"
          @click="activeTab = tab"
        >
          {{ tab }}
        </div>
      </div>

      <div class="tab__content">
        <br />
        <!-- <Login v-if="activeTab === 'Login'" /> -->
        <!--  <Register v-if="activeTab === 'Register'" /> -->
        <keep-alive>
          <component :is="activeTab" />
        </keep-alive>
      </div>
    </div>
  </div>
</template>

<script>
import Login from "./Login.vue";
import Register from "./Register.vue";
import ContactDetails from "./ContactDetails.vue";

export default {
  data() {
    return {
      msg: "Vue3 Bangla Tutorial",
      myComment: "",
      showDialog: false,
      notifications: [],
      tabs: ["Login", "Register"],
      activeTab: "Login"
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
    Login,
    Register,
    ContactDetails
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
</style>
