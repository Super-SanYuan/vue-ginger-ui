<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <hr />
    <g-form :model="formValidate" :rules="rulesValidate">
      <g-form-item label="用户名" prop="name">
        <!-- <g-input v-model="formValidate.name"></g-input> -->
        <input type="text" v-model="formValidate.name" />
      </g-form-item>
      <g-form-item label="邮箱" prop="email">
        <!-- <g-input v-model="formValidate.email"></g-input> -->
        <input type="text" v-model="formValidate.email" />
      </g-form-item>
    </g-form>
    <button @click="handleClick">CLick</button>
  </div>
</template>

<script>
import Form from "./components/Form/form";
import formItem from "./components/Form/form-item";
export default {
  name: "app",
  components: { "g-form": Form, "g-form-item": formItem },
  data() {
    return {
      formValidate: {
        name: "",
        email: ""
      },
      rulesValidate: {
        name: [{ requied: true, message: "用户名不能为空", trigger: "blur" }],
        email: [
          { required: true, message: "邮箱不能为空", trigger: "blur" },
          { type: "email", message: "邮箱格式不正确", trigger: "blur" }
        ]
      }
    };
  },
  mounted() {
    console.log(this.$options.name);
  },
  methods: {
    handleClick() {
      this.$emit("click", 1);
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
