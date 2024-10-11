<template>
  <div class="title">
    <div class="title__text">Что поесть?</div>

    <div class="title__description">
      <p>
        Сервис помогает вам выбрать то, что поесть, когда у вас закончились
        идеи.
      </p>
      <p>
        Тыкаете на кнопку - сайт предлагает вам блюдо и советует рецепт
      </p>
    </div>
  </div>

  <RecipeSelection />
</template>

<script setup>
import RecipeSelection from "./components/RecipeSelection.vue"
</script>

<style scoped lang="scss">
.title {
  &__text {
    font-size: 6rem;
  }

  &__description {
    display: grid;
    justify-items: start;
    gap: 20px;
    p {
      font-size: 16px;
      margin: 0;
    }
  }
}
</style>
