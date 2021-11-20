<template>
  <div class="the-card">
    <div class="the-card__title">
      {{ cardTitle }}
    </div>
    <div class="the-card__body">
      <slot>
        Default card content goes here
      </slot>
    </div>

    <div class="the-card__footer" v-if="$slots.footer">
      <slot name="footer"> </slot>
    </div>
  </div>
</template>

<script>
export default {
  mounted() {
    console.log(this.$slots.footer);
  },
  props: ["cardTitle"]
};
</script>

<style>
.the-card {
  width: 300px;
  border: 1px solid #006f88;
  min-height: 100px;
  margin: 22px auto;
}

.the-card__title {
  background: #167db1;
  padding: 5px 11px;
  color: #fff;
}

.the-card__body {
  padding: 11px;
}

.the-card__body img {
  height: 111px;
}

.the-card__footer {
  background: #e3e3e3;
  padding: 5px 11px;
  text-align: center;
}
</style>
