<script setup>
import CloseButton from "@/components/CloseButton.vue";

// information come from parent component (in this case it's the App.vue)
defineProps({
  task: Object,
});
</script>

<template>
  <li>
    <div :class="{ colored: task.isColored }" class="task">
      {{ task.name }}
      <!-- 'removeTask' = close-task that is in the father -->
      <CloseButton class="close-button" @click="$emit('removeTask')" />
    </div>
  </li>
</template>

<style scoped>
.task {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-top: 1rem;
  color: var(--blue);
  font-weight: 600;
  border: solid var(--blue-o) 1px;
  border-radius: 6px;
  padding: 1rem;
  font-size: 1rem;
  box-shadow: 0px 0px 4px rgb(161, 161, 161, 0.3);
  cursor: pointer;
}
.colored {
  text-decoration: line-through;
  color: var(--green);
}
.close-button {
  height: 1rem;
  padding: 0px;
  margin: 0px;
  cursor: pointer;
}
.close-button:hover {
  background-color: rgb(252, 211, 211);
  border-radius: 100%;
  width: 18px;
}
</style>
