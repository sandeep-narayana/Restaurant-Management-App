<template>
  <h1>Hello , Welcome on Home Page</h1>
</template>
<script>
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
};
</script>
