<template>
  <h1>Filters</h1>

  <p v-for="filter in filters" :key="filter">
    {{ filter }}
  </p>
</template>

<script>
const filters = [
  'Жадан',
  'Андрухович'
]

export default {
  data () {
    return {
      filters
    }
  }
}
</script>