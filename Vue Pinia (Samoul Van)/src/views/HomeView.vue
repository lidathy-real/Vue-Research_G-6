<template>
  <div class="home">
    <div class="count">
      {{ count }}
    </div>
    <div class="buttons">
      <button @click="decreaseCount">-</button>
      <button @click="increaseCount">+</button>
    </div>
    <hr>
    <div>
      This counter is: {{oddOrEven}}
    </div>
  </div>
</template>

<script setup>
import { ref,computed } from "vue";
const count = ref(0);
const increaseCount = () => {
  count.value++;
}
const decreaseCount = () => {
  count.value--;
};
const oddOrEven = computed (() => {
  if (count.value %2 === 0) return 'odd'
  return 'evend'
})
</script>
<style>
.count {
  font-size: 80px;
  margin: 20px;
  color: red;
}

.buttons button {
  font-size: 40px;
  margin: 10px;
}

</style>
