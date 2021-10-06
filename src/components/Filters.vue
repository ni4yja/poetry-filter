<template>
  <label for="search" style="font-size: 0">
    Пошук
    <input
      id="search"
      v-model="word"
      @keypress="search(word)"
      class="input m-3"
      type="text"
      placeholder="Пошук за назвою"
    />
  </label>
  <p v-for="filter in sorted" :key="filter" class="m-3">
    <span @click="() => filterPosts(filter)" class="tag is-medium is-link is-light">{{ filter }}</span>
  </p>
</template>

<script>
const filters = ["*Всі", "Жадан", "Андрухович", "Калитко", "Семенчук", "Іздрик", "Лазуткін", "Білоцерківець", "Шувалова"];
const sorted = filters.sort((a, b) => a.localeCompare(b))

export default {
  props: ["filterPosts", "search"],
  data() {
    return {
      sorted,
      word: ''
    };
  },
};
</script>