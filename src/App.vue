<template>
  <header>
    <h2>{{ msg }}</h2>
  </header>

  <div class="container">
    <h3>Credit Card Input</h3>
    <credit-card
      v-model:nameOnCard="nameOnCard"
      v-model:cardNumber="cardNumber"
      v-model:expiry="expiry"
      v-model:cvv="cvv"
    ></credit-card>
    <br />
    <hr />
    <br />

    <p>
      Name: {{ nameOnCard }} <br />
      Card Number: {{ cardNumber }} <br />
      Expiry: {{ expiry }} <br />
      CVV: {{ cvv }} <br />
    </p>
  </div>
</template>

<script>
import CreditCard from "./CreditCard.vue";

export default {
  data() {
    return {
      msg: "Vue3 Bangla Tutorial",
      nameOnCard: "Mr.",
      cardNumber: "",
      expiry: "",
      cvv: ""
    };
  },
  methods: {},
  components: {
    CreditCard
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
</style>
