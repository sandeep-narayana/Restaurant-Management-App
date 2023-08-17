<template>
<Headers/>
<h1>Hello {{this.name}}, Welcome to Update Restaurant Page</h1>
</template>
<script>
import Headers from "./Header.vue"
export default {
  name: "UpdateComponent",
  data() {
    return {
        name:""
    };
  },
  methods: {},
  mounted() {
    var user = localStorage.getItem("user-info");
    this.name = JSON.parse(user).name
  },
  components: {
    Headers
  },
};
</script>
