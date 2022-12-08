<script setup>
import { ref } from "vue";
//  const ✅
//  let ✅
// @click ✅
// function ✅
let number = ref(0);
let items = ref([1,2,3,4,5,6,7,8,9,10])
function increment(num) {
  number.value+= num
}

function decrement (num) {
  number.value-= num
}

</script>

<template>
  <div class="number">{{ number }}</div>
  <div class="wrapper">
    <div v-for="item in items" :key="item">
    <button @click="increment(item)"> Increment {{ item }} </button>
    <button @click="decrement(item)"> Decrement {{ item }} </button>
    </div>
  </div>

</template>

<style>
.number {
  color: white;
  font-size: 30px;
  font-weight: bold;
  margin-bottom: 20px;
  text-align: center;
  padding: 10px;
  background-color: darkmagenta;
}

.wrapper {
  display: flex;
  grid-gap: 100px;
}
</style>
