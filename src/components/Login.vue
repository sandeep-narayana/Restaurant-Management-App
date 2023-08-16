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
      <router-link to="/sign-up" >Not a memebr? go to Sign-Up</router-link>
    </p>
  </div>
</template>
<script>
export default {
  name: "loginC",
  data() {
    return {
      email: "",
      password: "",
    };
  },
  methods: {
    login() {
      //
    },
  },
};
</script>

