<template>
  <h2>Write your comment below</h2>
  <div class="the-comment">
    <textarea :value="modelValue" @input="handleInput" v-bind="$attrs" />

    <div class="text-right">
      <button @click="$emit('continueClick')">{{ buttonText }}</button>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    modelValue: {
      type: String,
      default: ""
    },
    buttonText: {
      type: String,
      default: "OK"
    }
  },
  inheritAttrs: false,
  created() {
    // console.log(this.$attrs);
  },

  methods: {
    handleInput(e) {
      this.$emit("update:modelValue", e.target.value);
    }
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
  // },
  // beforeUnmount() {
  //   console.log("beforeUnmount");
  // },
  // unmounted() {
  //   console.log("unmounted");
  // }
};
</script>

<style scoped>
.the-comment {
  width: 288px;
  border: 1px solid gray;
  padding: 22px;
  border-radius: 5px;
  background-color: rgb(255, 254, 247);
  color: rgb(82, 82, 82);
  min-height: 111px;
}

textarea {
  padding: 7px 9px;
  margin-bottom: 11px;
  border-radius: 3px;
  width: 100%;
  border: 1px solid gray;
}

.text-right {
  text-align: right;
}
</style>
