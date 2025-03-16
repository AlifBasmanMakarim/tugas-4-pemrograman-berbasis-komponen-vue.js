<script setup>
import { ref } from 'vue';

const count = ref(0);
const isClicked = ref(false);
const isLiked = ref(false);

function changeColor() {
  isClicked.value = !isClicked.value;
}

function toggleLike() {
  isLiked.value = !isLiked.value;
}
</script>

<template>
  <h1>Tambah {{ count }}</h1>

  <div class="card">
    <button type="button" @click="count++">Tambah {{ count }}</button>
  </div>

  <h1 :class="isClicked ? 'titleClicked' : 'title'">Make me red or blue</h1>
  <button @click="changeColor">Change Color</button>

  <br />
  <button @click="toggleLike">{{ isLiked ? 'Tidak Suka' : 'Suka' }}</button>
</template>

<style>
.title {
  color: green;
}
.titleClicked {
  color: red;
}
</style>