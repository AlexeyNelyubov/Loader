<script setup>
import { computed } from "vue";
import Loader from "./TheLoader.vue";
const props = defineProps({
  isEmptySearch: Boolean,
  showLoader: Boolean,
});

const messegeToShow = computed(() =>
  props.showLoader
    ? "Загружаем информацию о наших питомцах."
    : "К сожалению, отсутствуют результаты по вашему запросу. Попробуйте изменить параметры фильтров."
);
</script>

<template>
  <div class="empty-search" v-if="props.isEmptySearch">
    <Loader v-if="showLoader" />
    <h3 class="empty-search__message">{{ messegeToShow }}</h3>
    <img
      v-if="!showLoader"
      class="empty-search__icon"
      src="/src/assets/images/not_found.svg"
      alt="not found"
    />
  </div>
</template>

<style lang="scss">
.empty-search {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 480px;
  height: 457px;
  margin: auto;

  &__message {
    // @include Epilogue(700, 20px);
    text-align: center;
  }

  &__icon {
    width: 200px;
    height: 200px;
    margin-top: 50px;
  }
}
</style>
