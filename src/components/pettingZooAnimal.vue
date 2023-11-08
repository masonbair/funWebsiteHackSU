<template>
  <img @click="state.timesPet++" :src="state.imageUrl" />
  <p>Times the animal was pet: {{ state.timesPet }}</p>
</template>

<script setup>
import { reactive, watch } from 'vue';
const state = reactive({
  timesPet: 0,
  imageUrl: 'https://hacksu.com/animals/alpaca.jpg',
});

function maybeIrradiated() {
  if (Math.random() < 0.1) {
    state.imageUrl = 'https://hacksu.com/animals/alpaca-fire.gif';
  }
}

watch(state, maybeIrradiated);
</script>
