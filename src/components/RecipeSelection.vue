<template>
  <div class="recipe-selection">
    <div class="recipe-selection__button">
      <button>Показать рецепт</button>
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

    button {
      font-size: 60px;
      padding: 40px 20px;
      text-decoration: 3px underline;
      border: 2px solid #00ffa6;
      border-radius: 12px;
      background-color: transparent;
      color: #00ffa6;
      cursor: pointer;
      transition: background-color 0.7s;

      &:hover {
        background-color: #00ffa61f;
        // color: white;
      }
    }
  }
}
</style>
