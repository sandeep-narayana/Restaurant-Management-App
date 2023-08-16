<template>
  <div class="nav">
    <a href="home">Home</a>
    <a href="home">Add Restaurant</a>
    <a href="home">Update Restaurant</a>
    <a href="home">Logout</a>
  </div>
</template>
<script>
export default {
  name: "HeaderC",
  data() {
    return {};
  },
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
