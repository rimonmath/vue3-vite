<template>
  <div class="credit-card">
    <label> Name On Card </label>
    <input
      type="text"
      :value="nameOnCard"
      @input="handleInput('update:nameOnCard', $event)"
    />
    <br />

    <label> Card Number </label>
    <input
      type="text"
      :value="cardNumber"
      @input="handleInput('update:cardNumber', $event)"
    />

    <br />

    <div class="row">
      <div class="col-6">
        <label> Expiry </label>
        <input
          type="text"
          :value="expiry"
          placeholder="MM/YY"
          @input="handleInput('update:expiry', $event)"
        /><br />
      </div>

      <div class="col-6">
        <label> CVV </label>
        <input
          type="text"
          :value="cvv"
          @input="handleInput('update:cvv', $event)"
        />
        <br />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    nameOnCard: {
      type: String,
      default: ""
    },
    cardNumber: {
      type: String,
      default: ""
    },
    expiry: {
      type: String,
      default: ""
    },
    cvv: {
      type: String,
      default: ""
    }
  },
  methods: {
    handleInput(eventName, e) {
      //   console.log(e.target.value);
      this.$emit(eventName, e.target.value);
    }
  }
};
</script>

<style>
.credit-card {
  width: 288px;
  border: 1px solid gray;
  padding: 22px;
  border-radius: 5px;
  background-color: rgb(255, 254, 247);
  color: rgb(82, 82, 82);
  min-height: 111px;
}

input {
  padding: 7px 9px;
  margin-bottom: 11px;
  border-radius: 3px;
  width: 100%;
  border: 1px solid gray;
}

.row {
  display: flex;
}

.col-6 {
  flex: 1;
  padding: 0 2px;
}
</style>
