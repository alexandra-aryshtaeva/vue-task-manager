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
    <input type="text" placeholder="Enter new task" />
    <ul>
      <li><Task> </Task></li>
    </ul>
  </main>
</template>

<style scoped>
main {
  display: flex;
  flex-direction: column;
  margin: 0rem 0rem;
  padding-top: 0.12rem;
  width: 500px;
  height: 500px;
  background-color: white;
  border-radius: 1rem;
}
.title-wrapper {
  margin: 0rem 1rem;
}
h1 {
  font-size: 2rem;
  color: var(--green);
  text-align: center;
  background-color: aqua;
}

input {
  height: 35px;
  display: flex;
  border: solid rgb(156, 156, 156, 0.5) 1px;
  border-radius: 6px;
  padding-left: 1rem;
  box-shadow: 0px 0px 2px rgb(161, 161, 161, 0.5);
  display: flex;
  flex-direction: column;
  margin: 0rem 1rem;
}

input::placeholder {
  color: rgb(156, 156, 156);
  font-family: "Inter";
  font-size: 1rem;
  align-items: center;
}
</style>
