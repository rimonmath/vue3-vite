<template>
  <div class="credit-card">
    <label for="">Name On Card</label>
    <input
      type="text"
      :value="nameOnCard"
      @input="handleInput('update:nameOnCard', $event)"
    />
    <br />
    <label for="">Card Number</label>
    <input type="text" @input="handleInput('update:cardNumber', $event)" />
    <br />
    <div class="row">
      <div class="col-6">
        <label for="">Expiry</label>
        <input
          type="text"
          placeholder="MM/YY"
          @input="handleInput('update:expiry', $event)"
        />
      </div>

      <div class="col-6">
        <label for="">CVV</label>
        <input
          type="text"
          placeholder="XXX"
          @input="handleInput('update:cvv', $event)"
        />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    nameOnCard: {
      type: String,
      default: "",
    },
    cardNumber: {
      type: String,
      default: "",
    },
    expiry: {
      type: String,
      default: "",
    },
    cvv: {
      type: String,
      default: "",
    },
  },

  methods: {
    handleInput(emitEventName, event) {
      this.$emit(emitEventName, event.target.value);
    },
  },
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