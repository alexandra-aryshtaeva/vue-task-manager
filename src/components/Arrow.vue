<script setup>
const props = defineProps({
  direction: String,
  disabled: Boolean,
});

const emit = defineEmits(["change-offset"]);

function handleClick() {
  if (!props.disabled) {
    emit("change-offset");
  }
}
</script>

<template>
  <div @click="handleClick()">{{ direction }} - disabled => {{ disabled }}</div>
</template>

<style scoped>
div {
  border: solid salmon;
  background-color: aqua;
  display: flex;
  flex-direction: column;
  justify-self: center;
  text-align: center;
  cursor: pointer;
}
div:hover {
  background-color: antiquewhite;
}
</style>
