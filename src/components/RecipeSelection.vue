<template>
  <div class="recipe-selection">
    <div class="recipe-selection__button">
      <button>Показать рецепт</button>
    </div>

    <div class="recipe-selection__content">

    </div>
  </div>
</template>

<script setup>
import { defineComponent } from "vue"

defineComponent({
  name: "RecipeSelection",
})
</script>

<style scoped lang="scss">
.recipe-selection {
  margin: 40px 0;

  &__button {
    display: flex;
    justify-content: center;

    user-select: none;
    button {
      font-size: clamp(1rem, 3vw, 2.5rem);
      padding: clamp(1rem, 3vw, 3rem);

      text-decoration: clamp(1px, 2px, 10px) underline;
      border: 2px solid #00ffa6;
      border-radius: 12px;

      background-color: transparent;
      color: #00ffa6;

      cursor: pointer;

      transition: background-color 0.7s;

      &:hover {
        background-color: #00ffa61f;
      }
    }


  }

  &__content {

  }
}
</style>
