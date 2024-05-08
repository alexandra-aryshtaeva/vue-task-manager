<script setup>
import CloseButton from "@/components/CloseButton.vue";

const props = defineProps({
  options: Array,
});
</script>

<template>
  <ul>
    <li>
      <div class="task">Insert Task <CloseButton class="close-button" /></div>
    </li>
  </ul>
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
  font-size: 1.2rem;
  box-shadow: 0px 0px 4px rgb(161, 161, 161, 0.3);
}

.close-button {
  height: 1rem;
}
</style>
