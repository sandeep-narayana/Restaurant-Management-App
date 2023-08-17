<template>
  <Header />
  <h1>Hello {{ this.name }} , Welcome to Home Page</h1>
  <!-- table to show the data of different restaurants -->
  <table class="restaurant-table">
    <thead>
      <tr>
        <th>ID</th>
        <th>Name</th>
        <th>Address</th>
        <th>Contact</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="item in restaurants" :key="item.id">
        <td>{{ item.id }}</td>
        <td>{{ item.name }}</td>
        <td>{{ item.address }}</td>
        <td>{{ item.contact }}</td>
      </tr>
    </tbody>
  </table>
</template>
<script>
import Header from "./Header.vue";
import axios from "axios";
export default {
  name: "HomeC",
  data() {
    return {
      name: "",
      restaurants: [],
    };
  },
  methods: {},
  async mounted() {
    let user = localStorage.getItem("user-info");
    this.name = JSON.parse(user).name;
    if (!user) {
      this.$router.push({ name: "SignUp" });
    }

    // fetch all the restaurant data at the time of page load i.e at the time of mout
    var restaurants = await axios.get("http://localhost:3000/restaurants");
    this.restaurants = restaurants.data;
  },
  components: {
    Header,
  },
};
</script>
<style>
/* Style for the entire table */
.restaurant-table {
  width: 100%;
  border-collapse: collapse;
  border: 1px solid #ccc;
  margin-top: 20px;
  
}

/* Style for table header */
.restaurant-table th  {
  background-color: #f2f2f2;
  padding: 10px;
  text-align: left;
  font-weight: bold;
  border: 1px solid #ccc;
  text-align: center;
}

/* Style for table rows */
.restaurant-table td {
  padding: 10px;
  border: 1px solid #ccc;
}

/* Alternating row colors for better readability */
.restaurant-table tbody tr:nth-child(even) {
  background-color: #f2f2f2;
}
</style>
