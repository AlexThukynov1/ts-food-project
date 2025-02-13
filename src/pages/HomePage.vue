<template>
  <main>
    <form action="" @submit.prevent="addRestaurant">
      <label for="restaurent-name">Restaurant name</label>
      <input type="text" name="" id="restaurent-name" v-model="newRestaurantName" />
      <button type="submit">Add Restaurant</button>
    </form>
    <ul>
      <li v-for="restaurant of restaurantList" :key="restaurant">
        {{ restaurant }}
      </li>
    </ul>
  </main>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const newRestaurantName = ref<string>('')
const restaurantList = ref<string[]>([])

function addRestaurant() {
  restaurantList.value.push(newRestaurantName.value)
  newRestaurantName.value = ''
}
</script>

<style scoped></style>
