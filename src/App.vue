<template>
  <div class="wrapper">
    <div id="app">
      <h1>Practica 3 - Vue Counter</h1>
      <p>Counter: {{ counter }}</p>
      <button @click="increment">+</button>
      <button @click="decrement" :disabled="counter === 0">-</button>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';

const counter = ref<number>(0);

const increment = (): void => {
  counter.value++;
};

const decrement = (): void => {
  if (counter.value > 0) {
    counter.value--;
  }
};
</script>

<style scoped>
.wrapper {
  font-family: Arial, sans-serif;
  margin: 0;
  padding: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  background-color: #8b15da;
}

#app {
  text-align: center;
  padding: 20px;
  border: 1px solid #f5deff;
  border-radius: 8px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  background-color: rgba(255, 255, 255, 0.936);
}

button {
  margin: 5px;
  padding: 10px 15px;
  font-size: 16px;
  cursor: pointer;
  border: none;
  border-radius: 4px;
  background-color: #e6dd36;
  color: white;
  transition: background-color 0.3s ease;
}

button:hover {
  background-color: #e6dd36;
}

button:disabled {
  background-color: #ccc;
  cursor: not-allowed;
}
</style>