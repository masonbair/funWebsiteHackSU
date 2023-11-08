<template>
  <template v-if="!state.ignoredWarning">
    <!-- HTML content goes here -->
    <h1>Warning:</h1>
    <strong>Dangerous radiation levels detected.</strong>
    <h2>Flee immediately, {{ name }}!</h2>
    <ul>
      <li>Leave the room</li>
      <li>Leave the building</li>
      <li>If possible, leave the metropolitan area</li>
    </ul>
    <button @click="state.ignoredWarning = true">
      ignore warning and proceed to petting zoo
    </button>
  </template>

  <template v-else>
    <h2>Welcome to the petting zoo</h2>
    <PettingZooAnimal />
    <PettingZooAnimal />
  </template>
</template>

<script setup>
// JavaScript for interactive content goes here
const name = 'mason'; //prompt('What is your name?');

import { reactive } from 'vue';
import PettingZooAnimal from './pettingZooAnimal.vue';

const state = reactive({
  ignoredWarning: false,
});
</script>

<style scoped>
/* CSS for style & layout goes here */
h1 {
  color: red;
}

* {
  font-family: sans-serif;
}
</style>
