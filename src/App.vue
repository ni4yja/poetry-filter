<template>
  <section class="hero is-medium is-warning">
    <div class="hero-body">
      <h1 class="title">13 цитат про осінь</h1>
    </div>
  </section>
  <div class="container">
    <div class="columns">
      <div class="column posts mr-6">
        <Posts :posts="posts" />
      </div>
      <div class="column is-one-third filters mb-6">
        <Filters 
          :filterPosts="filterPosts"
          :search="search"
        />
      </div>
    </div>
  </div>
  <footer class="footer mt-4">
    <div class="content has-text-centered">
      <p>
        Made by <a href="https://twitter.com/ni4yja">ni4yja</a> based on <a href="https://www.youtube.com/watch?v=sJR3pVx-M58">Faraday Academy stream</a>
      </p>
    </div>
  </footer>
</template>

<script>
import Filters from "./components/Filters.vue";
import Posts from "./components/Posts.vue";

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
      this.resetPosts();
      if (authorName !== "*Всі") {
        this.posts = this.posts.filter((post) => {
          return post.author === authorName;
        });
      }
    },
    search (word) {
      this.resetPosts();
      this.posts = this.posts.filter((post) => {
        return post.title.toLowerCase().includes(word.toLowerCase());
      })
    },
    resetPosts () {
      this.posts = POETRY;
    }
  }
};
</script>

<style>
@media only screen and (max-width: 600px) {
  .columns {
    display: flex;
    flex-direction: column-reverse;
    margin: 0;
  }

  .posts {
    margin-right: 0 !important;
  }

  .filters {
    margin-bottom: 0 !important;
  }

  .filters p {
    display: inline-block; 
  }

  .input {
    margin: 0 !important;
  }
}
</style>
