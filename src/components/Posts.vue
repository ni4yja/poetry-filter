<template>
  <div
    v-for="post in posts"
    :key="post.id"
    class="card my-5"
  >
    <div class="card-content">
      <div class="content">
        <h2 class="title is-4">{{ post.title }}</h2>
        <p>{{ post.quote }}</p>
        <em>{{ post.author }}</em>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  props: [
    "posts"
  ]
}
</script>