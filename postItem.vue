<template>
  <div class="post">
    <div>
      <div><strong>Название:</strong>{{ post.title }}</div>
      <div><strong>Описание:</strong>{{ post.body }}</div>
    </div>
    <div class="post_btn">
      <Button>Удалить</Button>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    post: {
      type: Object,
      required: true,
    },
  },
};
</script>
<style scoped>
.post_btn button {
  background: #32c1f9;
  padding: 10px 15px;
  color: #fff;
  cursor: pointer;
  border-radius: 20px;
  transition: transform 500ms ease;
  border: 2px solid #32c1f9;
}

input {
  background-color: transparent;
  padding: 12px 18px;
  border-radius: 12px;
  border: 2px solid #f9c132;
  color: white;
  margin-right: 12px;
}

.post {
  display: flex;
  padding: 12px;
  border-radius: 8px;
  border: 2px solid black;
  margin-bottom: 14px;
  justify-content: space-between;
}
</style>
