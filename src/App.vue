<script setup>
import { ref } from "vue";
import Task from "./components/Task.vue";
import Arrow from "./components/Arrow.vue";
const newTask = ref("");
const offset = ref(0);

// props
const tasks = ref([{ name: "1: do laundry" }, { name: "2: wash dishes" }]);

function addTask() {
  if (newTask.value == "") {
    return;
  }

  tasks.value.push({
    name: newTask.value,
  });
  newTask.value = "";
}

/**
 * Removes task from list.
 * @param task Task to close
 */
function remove(task) {
  tasks.value.splice(tasks.value.indexOf(task), 1);
}
</script>

<template>
  <main>
    <div class="title-wrapper"><h1>Todo-List</h1></div>
    <input
      v-model="newTask"
      type="text"
      placeholder="Enter new task"
      @keydown.enter="addTask"
    />

    <TransitionGroup name="fade" tag="ul">
      <Task
        v-for="(task, idx) in tasks.slice(offset, offset + 4)"
        :key="idx"
        @click="task.isColored = !task.isColored"
        :task="task"
        @remove-task="remove(task)"
      />
    </TransitionGroup>

    <Arrow
      :disabled="tasks.length <= 4 || tasks.length - offset == 4"
      @change-offset="offset++"
      direction="down"
    />

    <Arrow
      :disabled="tasks.length <= 4 || offset <= 0"
      direction="up"
      @change-offset="offset--"
    />
  </main>
</template>

<style scoped>
ul {
  padding: 0;
  margin: 0 1rem;
}
main {
  display: flex;
  flex-direction: column;
  margin: 0 auto;
  padding-top: 0.12rem;
  width: 500px;
  height: 500px;
  background-color: white;
  border-radius: 1rem;
  box-shadow: 2px 2px 10px var(--blue);
}
.title-wrapper {
  margin: 0rem 1rem;
}
h1 {
  font-size: 2rem;
  color: var(--green);
  text-align: center;
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

.fade-enter-from {
  opacity: 0;
}
.fade-enter-to {
  opacity: 1;
}
.fade-enter-active {
  transition: all 0.5s ease;
}

.fade-leave-from {
  opacity: 1;
}
.fade-leave-to {
  opacity: 0;
}
.fade-leave-active {
  transition: all 0.3s ease;
}
</style>
