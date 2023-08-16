<template>
  <img class="logo" alt="Vue logo" src="../assets/logo.png" />
  <h1>Sign Up</h1>
  <div class="resgister">
    <input type="text" placeholder="Enter your Name" />
    <input type="email" placeholder="Enter your Email" />
    <input type="password" placeholder="Enter your Password" />
    <button>Sign Up</button>
  </div>
</template>
<script>
export default {
  name: "SignUp",
};
</script>
<style scoped>
.logo {
  width: 100px;
}
.resgister input {
  width: 300px;
  height: 40px;
  padding-left: 20px;
  display: block;
  margin: auto;
  margin-bottom: 20px;
  border: 1px solid green;
}
.resgister button {
    width: 325px;
    height: 40px;
    color: red;
    background-color: skyblue;
    border: none;
    box-shadow: 10px 5px 5px red;
    cursor: pointer;
}
</style>
