<template>
  <div class="recipe-selection">
    <div class="recipe-selection__button">
      <button @click="showNewRecipe">Показать блюдо</button>
    </div>

    <div class="recipe-selection__content">
      <span>{{ randomRecipe.name }}</span>

      <img :src="randomRecipe.image" :alt="randomRecipe.name" />
      <div class="attribution">
        <span
          >Все изображения взяты с сайта &nbsp;
          <a href="http://www.freepik.com/">Freepik</a>
        </span>
      </div>
      <!-- <img
        src="https://images.unsplash.com/photo-1512621776951-a57141f2eefd?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=387&q=80"
        :alt="randomRecipe.name"
      /> -->
    </div>
  </div>
</template>

<script setup>
import { defineComponent, ref } from "vue"
import { recipes } from "../data/food.js"

// функция для отоброжения нового рецепта
const randomRecipe = ref(recipes[Math.floor(Math.random() * recipes.length)])
function showNewRecipe() {
  randomRecipe.value = recipes[Math.floor(Math.random() * recipes.length)]
}

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
      font-size: clamp(1rem, 3vw, 2rem);
      padding: clamp(1rem, 3vw, 1.7rem);

      // text-decoration: clamp(1px, 2px, 10px) underline;
      border: 2px solid #00ffa6;
      border-radius: 12px;

      background-color: transparent;
      color: #00ffa6;

      cursor: pointer;

      transition: background-color 0.7s;

      &:hover {
        background-color: #00ffa649;
      }
    }
  }

  &__content {
    display: flex;
    flex-direction: column;
    align-items: center;

    margin-top: 20px;

    span {
      font-size: clamp(1rem, 3vw, 2rem);
      font-weight: 600;

      margin-bottom: 10px;
    }

    img {
      // width: 500px;
      width: clamp(300px, 50vw, 500px);
      height: auto;

      animation: fadeIn 2s;
      // margin-bottom: 20px;
    }

    // a {
    //   font-size: 20px;
    //   text-decoration: none;
    //   color: #00ffa6;

    //   &:hover {
    //     color: #9bfbda;
    //   }
    // }

    .attribution {
      display: flex;
      justify-content: center;
      align-items: baseline;

      span {
        font-size: 12px;
      }
      a {
        font-size: 12px;
        color: #00ffa6;
      }
    }
  }
}

@keyframes fadeIn {
  from {
    opacity: 0;
  }

  to {
    opacity: 1;
  }
}
</style>
