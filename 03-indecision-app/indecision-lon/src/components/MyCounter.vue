<template>
  <section>
    <h3>Counter: {{ counter }}</h3>
    <h3>Square: {{ squareCounter }}</h3>

    <div>
      <button v-on:click="counter++">+1</button>
      <button @click="counter--">-1</button>
    </div>
  </section>
</template>

<script setup lang="ts">
import { computed, ref } from 'vue';

// Define the props with TypeScript interface
//-------------------------------------------
interface Props {
  // value?: number;
  value: {
    type: Number;
    required: true;
  };
}
const props = defineProps<Props>();
//-------------------------------------------
// Define the props with TypeScript
//-------------------------------------------
// const props = defineProps({
//   value: {
//     type: Number,
//     required: true,
//   },
// });
//-------------------------------------------

const counter = ref(props.value ?? 0);
const squareCounter = computed(() => counter.value * counter.value);
</script>
<style scoped>
h1 {
  color: #42b983;
}
</style>
