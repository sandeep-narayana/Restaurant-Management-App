<template>
  <img class="logo" alt="Vue logo" src="../assets/logo.png" />
  <h1>Sign Up</h1>
  <div class="resgister">
    <input type="text" placeholder="Enter your Name" v-model="name" />
    <input type="email" placeholder="Enter your Email" v-model="email" />
    <input
      type="password"
      placeholder="Enter your Password"
      v-model="password"
    />
    <button v-on:click="signUp()">Sign Up</button>
  </div>
</template>
<script>
import axios from "axios";
export default {
  name: "SignUp",
  data() {
    return {
      name: "",
      email: "",
      password: "",
    };
  },
  methods: {
    async signUp() {
      // call api after istalling axios
      var result = await axios.post("http://localhost:3000/users", {
        name: this.name,
        email: this.email,
        password: this.password,
      });

      // store in localstorage so it can be used further
      localStorage.setItem("user-info", JSON.stringify(result.data));

      if (result.status === 201) {
        // if success redirect to home page
        this.$router.push({ name: "Home" });
      }
    },
  },
  mounted(){
    let user = localStorage.getItem("user-info");
    if(user){
      this.$router.push({name:"Home"})
    }
  }
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
