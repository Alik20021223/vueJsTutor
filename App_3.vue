<template>
  <div class="app">
    <PostForm @create="createPost" />
    <PostList :data="posts" />
  </div>
</template>
<script>
import PostForm from "./components-2/postForm.vue";
import PostList from "./components-2/postList.vue";

export default {
  components: { PostForm, PostList },
  data() {
    return {
      posts: [
        { id: 1, title: "Javascript", body: "Описание поста" },
        { id: 2, title: "VueJs", body: "Описание поста" },
        { id: 3, title: "ReactJs", body: "Описание поста" },
      ],
      title: "",
      body: "",
    };
  },
  methods: {
    createPost(post) {
      this.posts.push(post)
    },
  },
};
</script>
<style scoped>
.app {
  display: flex;
  flex-direction: column;
}
</style>
