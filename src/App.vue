<template>
  <div class="container">
    <div class="half">
      <Filters :filterPosts="filterPosts" />
    </div>
    <div class="half">
      <Posts :posts="posts"/>
    </div>
  </div>
</template>

<script>
import Filters from "./components/Filters.vue";
import Posts from "./components/Posts.vue";

//import MOCK_DATA from "./MOCK_DATA.json"
import POETRY from "./POETRY.json"

export default {
  name: "App",
  components: {
    Filters,
    Posts,
  },
  data () {
    return {
      posts: POETRY
    }
  }
};
</script>

<style scoped>
.container {
  display: flex;
  margin: 20px;
}

.half {
  width: 40%;
}
</style>
