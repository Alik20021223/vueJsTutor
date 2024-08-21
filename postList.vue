<template>
  <PostItem v-for="post in data" key="post.id" :post="post"/>
</template>
<script>
import PostItem from "./postItem.vue";

export default {
  components: { PostItem },
  props: {
    data: {
      type: Array,
      required: true,
    },
  },
};
</script>
<style></style>
