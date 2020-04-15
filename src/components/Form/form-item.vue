<template>
  <div>
    <label v-if="label">{{ label }}</label>
    <div>
      <slot></slot>
    </div>
  </div>
</template>

<script>
import Emitter from "../../mixins/emitter";
export default {
  name: "gFormItem",
  mixins: [Emitter],
  props: {
    label: {
      type: String,
      default: ""
    },
    prop: {
      type: String
    }
  },
  mounted() {
    if (this.porp) {
      this.dispatch("gForm", "on-form-item-add", this);
    }
  },
  beforeDestroy() {
    this.dispatch("gForm", "on-form-item-remove", this);
  }
};
</script>

<style>
</style>