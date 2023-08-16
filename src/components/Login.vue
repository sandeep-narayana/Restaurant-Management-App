<template>
  <img class="logo" alt="Vue logo" src="../assets/logo.png" />
  <h1>Login</h1>
  <div class="login">
    <input type="email" placeholder="Enter your Email" v-model="email" />
    <input
      type="password"
      placeholder="Enter your password"
      v-model="password"
    />
    <button v-on:click="login()">login</button>
    <p>
      <router-link to="/sign-up">Not a memebr? go to Sign-Up</router-link>
    </p>
  </div>
</template>
<script>
import axios from "axios";
export default {
  name: "loginC",
  data() {
    return {
      email: "",
      password: "",
    };
  },
  methods: {
    async login() {
      // go to documnetation and check filter API
      // change the use of litralls
      console.log(this.email, this.password);
      var result = await axios.get(
        `http://localhost:3000/users?email=${this.email}&&password=${this.password}`
      );
      console.log(result.data);

      if ((result.status == 200) & (result.data.length > 0)) {
        localStorage.setItem("user-info", JSON.stringify(result.data[0])); // as data in the form of array
        this.$router.push({ name: "Home" });
      }
    },
  },
  mounted() {
    let user = localStorage.getItem("user-info");
    if (user) {
      this.$router.push({ name: "Home" });
    }
  },
};
</script>

