<template>
  <router-view />
</template>

<script>
export default {
  name: "App",
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.logo {
  width: 100px;
}
.resgister input ,.login input {
  width: 300px;
  height: 40px;
  padding-left: 20px;
  display: block;
  margin: auto;
  margin-bottom: 20px;
  border: 1px solid green;
}
.resgister button, .login button {
  width: 325px;
  height: 40px;
  color: red;
  background-color: skyblue;
  border: none;
  box-shadow: 10px 5px 5px red;
  cursor: pointer;
}
</style>
