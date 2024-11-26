<script setup lang="ts">
import { ref } from 'vue';
import Booktable from './components/Booktable.vue';
import Bookcard from './components/Bookcard.vue';
import books from "./bookdata"

const isTableView = ref(false)
</script>

<template>
  <button @click="isTableView = !isTableView">
    {{ isTableView ? "Switch to card view" : "Switch to table view" }}
  </button>
  <Booktable v-if="isTableView" :books="books"/>
  <Bookcard v-else :books="books"/>
</template>

<style scoped>
  button{
    background-color: blue;
    border: none;
    border-radius: 5px;
    min-height: fit-content;
    max-height: 5vh;
    padding: 10px;
  }
</style>
