<template>
  <Header />
  <h1>Hello {{this.name}}, Welcome to Update Restaurant Page</h1>
</template>
<script>
import Header from "./Header.vue";
export default {
  name: "AddC",
  data() {
    return {
      name:""
    };
  },
  mounted() {
    var user = localStorage.getItem("user-info")
    this.name = JSON.parse(user).name
  },
  components: {
    Header,
  },
};
</script>
