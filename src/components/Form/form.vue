<template>
  <form>
    <slot></slot>
  </form>
</template>

<script>
export default {
  name: "gForm",
  props: {
    model: {
      type: Object
    },
    rules: {
      type: Object
    }
  },
  created() {
    this.$on("on-form-item-add", field => {
      if (field) this.field.push(field);
    });
    this.$on("on-form-item-remove", field => {
      if (field.prop) this.field.splice(this.field.indexOf(field), 1);
    });
  }
};
</script>

<style lang="less">
</style>