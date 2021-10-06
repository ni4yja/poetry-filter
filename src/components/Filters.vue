<template>
  <p v-for="filter in sorted" :key="filter" @click="() => filterPosts(filter)">
    {{ filter }}
  </p>
</template>

<script>
const filters = ["*Всі", "Жадан", "Андрухович", "Калитко", "Семенчук", "Іздрик", "Лазуткін", "Білоцерківець", "Шувалова"];
const sorted = filters.sort((a, b) => a.localeCompare(b))

export default {
  props: ["filterPosts"],
  data() {
    return {
      sorted
    };
  },
};
</script>