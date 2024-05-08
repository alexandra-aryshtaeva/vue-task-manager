<script setup>
import { ref } from "vue";
import Task from "./components/Task.vue";

const input = ref(" ");
const list = ref(" ");

function addTask() {}
</script>

<template>
  <main>
    <div class="title-wrapper"><h1>Todo-List</h1></div>
    <Task> </Task>
  </main>
</template>

<style scoped>
.title-wrapper {
  margin: 0rem 1rem;
}
h1 {
  font-size: 2rem;
  color: var(--green);
}
main {
  padding-top: 0.12rem;
  width: 500px;
  height: 500px;
  background-color: white;
  border-radius: 1rem;
}
</style>
