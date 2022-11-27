<script setup>
import { ref } from 'vue'
import EliminationVisualiser from './components/EliminationVisualiser.vue'

// See: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/random#getting_a_random_integer_between_two_values_inclusive
const numGifts = ref(Math.floor(Math.random() * 29 + 2))
</script>

<template>
  <div class="text-center flex flex-col gap-4 items-center">
    <h1 class="mt-3 text-3xl font-bold">Find Joseph's Gift</h1>
    <div class="flex justify-center items-center">
      <label for="numGifts">Pick a number from 2 to 30:</label>
      <input
        type="range"
        id="numGifts"
        class="ml-2 p-1 border-2 border-gray-dark"
        min="2"
        max="30"
        v-model.number="numGifts"
      />
    </div>
    <EliminationVisualiser :num-gifts="numGifts" />
  </div>
</template>
