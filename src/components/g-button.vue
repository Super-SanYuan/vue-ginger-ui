<template>
  <button :class="'g-btn g-btn-' + type" @click="onClick" :disabled="disabled">
    <span><slot>提交</slot></span>
  </button>
</template>

<script>
function vSize(val, target) {
  return target.some(i => i === val);
}
export default {
  props: {
    type: {
      type: String,
      default: "default",
      validator(val) {
        return vSize(val, ["primary", "dashed", "default"]);
      }
    },
    disabled: {
      type: Boolean,
      default: false
    }
  },
  methods: {
    onClick() {
      this.$emit("click");
    }
  }
};
</script>

<style scoped>
.g-btn {
  /* default */
  line-height: 1.499;
  position: relative;
  display: inline-block;
  font-weight: 400;
  white-space: nowrap;
  text-align: center;
  background-image: none;
  border: 1px solid transparent;
  cursor: pointer;
  height: 32px;
  padding: 0 15px;
  font-size: 14px;
  border-radius: 4px;
  color: rgba(0, 0, 0, 0.65);
  background-color: #fff;
  border-color: #d9d9d9;
}
.g-btn-default {
  color: rgba(0, 0, 0, 0.65);
  background-color: #fff;
  border-color: #d9d9d9;
}
.g-btn-primary {
  color: #fff;
  background-color: #1890ff;
  border-color: #1890ff;
}
.g-btn-dashed {
  color: #f5222d;
  background-color: #f5f5f5;
  border-color: #d9d9d9;
}
</style>
