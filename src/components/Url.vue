<template>
  <h1>Рецепта пока нет, готовьте по картинке</h1>

  <button class="close" @click="close">Закрыть</button>
</template>

<script setup>
import { defineProps } from "vue"

defineProps({
  close: Function,
})
</script>

<style scoped lang="scss">
h1 {
  font-size: 28px;
}

.close {
  font-size: 20px;
  padding: 5px;

  border: 2px solid #00ffa6;
  border-radius: 12px;

  background-color: transparent;
  color: #00ffa6;

  cursor: pointer;
}
</style>
