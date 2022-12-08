<script setup>
import { ref } from "vue";
//  const ✅
//  let ✅
// @click ✅
// function ✅
let number = ref(0);

function increment() {
  number.value++;
}

function decrement() {
  number.value--;
}

function increment_by_two() {
  number.value += 2;
}

function decrement_by_two() {
  number.value -= 2;
}
</script>

<template>
  <div class="number">{{ number }}</div>
  <div class="wrapper">
    <button @click="increment()">Increment</button>
    <button @click="decrement()">Decrement</button>
    <button @click="increment_by_two()">Increment by 2</button>
    <button @click="decrement_by_two()">Decrement by 2</button>
  </div>
</template>

<style>
.number {
  color: white;
  font-size: 50px;
  font-weight: bold;
  margin-bottom: 20px;
  text-align: center;
  padding: 10px;
  background-color: green;
}

.wrapper {
  display: flex;
  grid-gap: 40px;
}
</style>
