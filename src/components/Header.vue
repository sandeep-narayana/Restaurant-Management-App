<template>
  <div class="nav">
    <a href="/">Home</a>
    <a href="/add-restaurant">Add Restaurant</a>
    <a href="/update-restaurant">Update Restaurant</a>
    <a v-on:click="logout" href="#">Logout</a>
  </div>
</template>
<script>
export default {
  name: "HeaderC",
  data() {
    return {};
  },
  methods:{
    logout(){
      // delete the storage from local storage
      localStorage.clear();
      // redirect to login page
      this.$router.push({name:"Login"})
    }
  }
};
</script>
<style scoped>
.nav {
  background-color: #333;
  overflow: hidden;
  padding: 10px; /* Add padding around the content */
}

.nav a {
  color: white;
  padding: 15px; /* Increase the padding for links */
  text-decoration: none;
  transition: background-color 0.3s, color 0.3s;
  font-weight: bold; /* Make the text bold */
  font-size: 22px;
  margin-left: 50px;
}

.nav a:hover {
  background-color: white;
  color: #333;
}
</style>
