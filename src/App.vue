<template>
  <section class="hero is-medium is-warning">
    <div class="hero-body">
      <h1 class="title">13 цитат про осінь</h1>
    </div>
  </section>
  <div class="container">
    <div class="columns">
      <div class="column is-one-third">
        <Filters :filterPosts="filterPosts" />
      </div>
      <div class="column">
        <Posts :posts="posts" />
      </div>
    </div>
  </div>
</template>

<script>
import Filters from "./components/Filters.vue";
import Posts from "./components/Posts.vue";

//import MOCK_DATA from "./MOCK_DATA.json"
import POETRY from "./POETRY.json";

export default {
  name: "App",
  components: {
    Filters,
    Posts,
  },
  data() {
    return {
      posts: POETRY,
    };
  },
  methods: {
    filterPosts(authorName) {
      this.posts = POETRY;
      if (authorName !== "*Всі") {
        this.posts = this.posts.filter((post) => {
          return post.author === authorName;
        });
      }
    },
  },
};
</script>
