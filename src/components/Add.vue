<template>
  <Header />
  <div>
    <form class="restaurant-form" @submit.prevent>
      <label for="name" class="centered-label">Name:</label>
      <input
        type="text"
        id="name"
        class="input-field"
        placeholder="Enter the name of the restaurant"
        v-model="restaurant.name"
      />

      <label for="address" class="centered-label">Address:</label>
      <input
        type="text"
        id="address"
        class="input-field"
        placeholder="Enter the address of the restaurant"
        v-model="restaurant.address"
      />

      <label for="contact" class="centered-label">Contact:</label>
      <input
        type="text"
        id="contact"
        class="input-field"
        placeholder="Enter the contact of the restaurant"
        v-model="restaurant.contact"
      />

      <button class="submit-button" v-on:click="addRestaurant()">Submit</button>
    </form>
  </div>
</template>

<script>
import axios from "axios";
import Header from "./Header.vue";
export default {
  name: "AddC",
  data() {
    return {
      username: "",
      restaurant: {
        name: "",
        address: "",
        contact: "",
      },
    };
  },
  mounted() {
    var user = localStorage.getItem("user-info");
    this.username = JSON.parse(user).name;
  },
  components: {
    Header,
  },
  methods: {
    async addRestaurant() {
      var res = await axios.post("http://localhost:3000/restaurants",this.restaurant);
      if (res != null) {
        alert("Restaurant added successfully");
      } else {
        alert("Error");
      }
    },
  },
};
</script>
<style>
/* Style for the form container */
.restaurant-form {
  max-width: 400px;
  margin: 20px auto;
  padding: 50px;
  border: 1px solid #ccc;
  border-radius: 5px;
  background-color: #f7f7f7;
}

/* Center align the labels */
.centered-label {
  display: block;
  text-align: left;
  margin-bottom: 5px;
}

/* Style for form inputs */
.input-field {
  width: 100%;
  padding: 10px;
  margin: 10px;
  border: 1px solid #ccc;
  border-radius: 5px;
}

/* Style for the submit button */
.submit-button {
  background-color: #007bff;
  color: white;
  border: none;
  padding: 10px 20px;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.submit-button:hover {
  background-color: #0056b3;
}
</style>