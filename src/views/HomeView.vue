<template>
  <div class="home">
    <h1>Home</h1>
    <PostList v-if="showPosts" :posts="posts"></PostList>
    <button @click="showPosts = !showPosts">Toggle</button>
    <button @click="posts.pop()">Delete</button>
  </div>
</template>

<script>
import { ref } from 'vue';
import PostList from "../components/PostList.vue";

export default {
  name: "HomeView",
  components: { PostList },
  setup() {
      const posts = ref([
          { title: "Welcome to the blog", body: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Platea dictumst vestibulum rhoncus est pellentesque. Velit ut tortor pretium viverra suspendisse potenti nullam ac. Pharetra convallis posuere morbi leo urna. Aliquam ut porttitor leo a diam sollicitudin tempor id. Quam quisque id diam vel quam elementum pulvinar. Elit duis tristique sollicitudin nibh sit amet. Quis risus sed vulputate odio ut enim blandit volutpat. Suspendisse in est ante in. In vitae turpis massa sed elementum tempus egestas sed. Facilisis mauris sit amet massa vitae. Est placerat in egestas erat. Penatibus et magnis dis parturient montes nascetur ridiculus mus mauris.", id: 1 },
          { title: "Top 5 css tips", body: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Platea dictumst vestibulum rhoncus est pellentesque. Velit ut tortor pretium viverra suspendisse potenti nullam ac. Pharetra convallis posuere morbi leo urna. Aliquam ut porttitor leo a diam sollicitudin tempor id. Quam quisque id diam vel quam elementum pulvinar. Elit duis tristique sollicitudin nibh sit amet. Quis risus sed vulputate odio ut enim blandit volutpat. Suspendisse in est ante in. In vitae turpis massa sed elementum tempus egestas sed. Facilisis mauris sit amet massa vitae. Est placerat in egestas erat. Penatibus et magnis dis parturient montes nascetur ridiculus mus mauris.", id: 2 }
      ]);

      const showPosts = ref(true)

      return { posts, showPosts };
  },
}
</script>
