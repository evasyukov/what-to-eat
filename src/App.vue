<template>
  <div class="title">
    <div class="title__text">Что поесть?</div>

    <div class="title__description">
      <p>
        Сервис помогает вам выбрать то, что поесть, когда у вас закончились
        идеи.
      </p>
      <p>Тыкаете на кнопку - сайт предлагает вам блюдо и советует рецепт</p>
    </div>
  </div>

  <RecipeSelection />
</template>

<script setup>
import RecipeSelection from "./components/RecipeSelection.vue"
</script>

<style scoped lang="scss">
.title {
  display: flex;
  flex-direction: column;
  align-items: center;

  &__text {
    font-size: clamp(3rem, 8vw, 6rem);
  }

  &__description {
    display: flex;
    flex-direction: column;
    gap: 10px;

    width: 80%;

    text-align: left;
    
    p {
      font-size: clamp(10px, 1.5vw, 18px);

      padding: 0 10px;
      margin: 0;
    }
  }
}
</style>
