<template>
  <p v-for="filter in sorted" :key="filter" @click="() => filterPosts(filter)" class="m-3">
    <span class="tag is-medium is-link is-light">{{ filter }}</span>
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