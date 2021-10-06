<template>
  <div
    v-for="post in posts"
    :key="post.id"
  >
    <h2>{{ post.title }}</h2>
    <p>{{ post.quote }}</p>
  </div>
</template>

<script>

export default {
  props: [
    "posts"
  ]
}
</script>