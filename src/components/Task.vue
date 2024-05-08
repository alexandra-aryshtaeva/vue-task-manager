<script setup></script>

<template>
  <div class="wrapper">
    <input type="text" />
    <div class="task">Insert Task</div>
  </div>
</template>

<style scoped>
.wrapper {
  background-color: aqua;
  display: flex;
  flex-direction: column;
  margin: 1rem 1rem;
}
input {
  margin-top: 1rem;
  display: flex;
}

.task {
  margin-top: 1rem;
  border: solid black 1px;
  border-radius: 4px;
  text-align: center;
  padding: 1rem;
}
</style>
