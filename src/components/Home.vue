<template>
<Header/>
  <h1>Hello , Welcome on Home Page</h1>
</template>
<script>
import Header from "./Header.vue"
export default {
  name: "HomeC",
  data() {
    return {};
  },
  methods: {},
  mounted() {
    let user = localStorage.getItem("user-info");
    if (!user) {
      this.$router.push({ name: "SignUp" });
    }
  },
  components:{
    Header
  }
};
</script>
