<!-- <template>
  <div :class="containerClasses" :style="containerStyles">
    <h1>{{ header }}</h1>
    <div class="input-group">
      <input type="text" v-model="newItem" name="text" id="inp" placeholder="Add an item" class="form-control">
      <button class="btn btn-outline-secondary bg-primary" style="color: aliceblue;">Add</button>
    </div>

    <ul>
      <li v-for="item in items">
        {{ item.label }}
        
      </li>
      <div>{{ newItem }}</div>
      
    </ul>
  </div>
</template>

<script setup>
// Styles and classes for container
const containerClasses = "container bg-white position-absolute top-50 start-50 translate-middle shadow mb-5 bg-body-tertiary rounded"
const containerStyles = {
  borderRadius: "5px",
  margin: "10px",
  padding: "80px",
  width: "fit-content",
}
import { ref } from 'vue';
const header = ref('Shopping list app')
const items = ref([
  {
    id: 1,
    label: "10 party hats"
  },
  {
    id: 2,
    label: "2 board games"
  },
  {
    id: 3,
    label: "20 cups"
  }
])
// Creating a new item
const newItem = ref('');
</script>
<style computed>
.container {
  margin: auto;

}
</style> -->

<template>
  <div :class="containerClasses" :style="containerStyles">
    <h1>{{ header }}</h1>
    <div class="input-group">
      <input type="text" v-model="newItem" name="text" id="inp" placeholder="Add an item" class="form-control">
      <button @click="addItem" class="btn btn-outline-secondary bg-primary" style="color: aliceblue;">Add</button>
    </div>

    <ul>
      <li v-for="item in items" :key="item.id">
        {{ item.label }}
      </li>
    </ul>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const containerClasses = "container bg-white position-absolute top-50 start-50 translate-middle shadow mb-5 bg-body-tertiary rounded"
const containerStyles = {
  borderRadius: "5px",
  margin: "10px",
  padding: "80px", // Adjusted padding for better visibility
  width: "fit-content",
}

const header = ref('Shopping list app')
const items = ref([
  { id: 1, label: "10 party hats" },
  { id: 2, label: "2 board games" },
  { id: 3, label: "20 cups" }
])

const newItem = ref('');

const addItem = () => {
  if (newItem.value.trim() !== '') {
    items.value.push({ id: items.value.length + 1, label: newItem.value });
    newItem.value = '';
  }
}
</script>

<style>
.container {
  margin: auto;
}
</style>
