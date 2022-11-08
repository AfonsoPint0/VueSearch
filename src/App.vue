<template>
  <div id="app">
    <input type="text" v-model="search" />
    <div v-for="post in filteredPosts" :key="post.id">
      <post :post="post"></post>
    </div>
  </div>
</template>

<script>
import Post from "./components/Post";
export default {
  name: "App",
  components: { Post },
  data() {
    return {
      search: "",
      posts: [
        {
          id: 0,
          title: "0",
          body: "Box",
        },
        {
          id: 1,
          title: "1",
          body: "Rope",
        },
        {
          id: 2,
          title: "2",
          body: "Plank",
        },
      ],
    };
  },
  computed: {
    filteredPosts() {
      return this.posts.filter((post) =>
        post.body.toLowerCase().includes(this.search.toLowerCase())
      );
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
