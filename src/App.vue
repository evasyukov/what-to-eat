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
  <button class="to-recipe" @click="isShow = !isShow">Перейти к рецепту</button>

  <div class="modal-overlay" v-if="isShow">
    <div class="modal-overlay__content">
      <Url :close="closeModal" />
    </div>
  </div>

  <!-- <Url v-if="isShow "/> -->
</template>

<script setup>
import { ref } from "vue"

import RecipeSelection from "./components/RecipeSelection.vue"
import Url from "./components/Url.vue"

const isShow = ref(false)

const closeModal = () => {
  isShow.value = false
}
</script>

<style scoped lang="scss">
.title {
  display: flex;
  flex-direction: column;
  align-items: center;

  &__text {
    font-size: clamp(3rem, 8vw, 6rem);
    color: #00ffa6;
    user-select: none;
  }

  &__description {
    display: flex;
    flex-direction: column;
    gap: 10px;

    width: 80%;

    text-align: left;

    p {
      font-size: clamp(12px, 1.5vw, 18px);

      padding: 0 10px;
      margin: 0;
    }
  }
}
.to-recipe {
  font-size: clamp(16px, 2vw, 22px);
  border: none;
  cursor: pointer;
  // padding: clamp(1rem, 3vw, 1.7rem);
  // border: 2px solid #00ffa6;
  // border-radius: 12px;

  background-color: transparent;
  color: #00ffa6;

  &:hover {
    color: #9bfbda;
    text-decoration: underline;
  }
}

.modal-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  display: flex;
  justify-content: center;
  align-items: center;

  &__content {
    background-color: #242424;
    padding: 20px;
    border-radius: 10px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
    width: 80%;
    max-width: 500px;
  }
}
</style>
