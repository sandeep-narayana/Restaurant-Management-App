<template>
<Header/>
  <h1>Hello {{this.name}} , Welcome to Home Page</h1>
</template>
<script>
import Header from "./Header.vue"
export default {
  name: "HomeC",
  data() {
    return {
      name:""
    };
  },
  methods: {},
  mounted() {
    let user = localStorage.getItem("user-info");
    this.name = JSON.parse(user).name
    if (!user) {
      this.$router.push({ name: "SignUp" });
    }
  },
  components:{
    Header
  }
};
</script>
