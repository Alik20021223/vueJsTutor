<template>
  <form @submit.prevent>
    <h4>Создание поста</h4>
    <input
      v-model="post.title"
      type="text"
      class="input"
      placeholder="Название"
    />
    <input
      v-model="post.body"
      type="text"
      class="input"
      placeholder="Описание"
    />
    <button class="btn" @click="createPost">Создать</button>
  </form>
</template>
<script>
export default {
  data() {
    return {
      post: {
        title: "",
        body: "",
      },
    };
  },
  methods: {
    createPost() {
      this.post.id = Date.now();
      this.$emit("create", this.post);
      this.post = {
        title: "",
        body: "",
      };
    },
  },
};
</script>
<style scoped>
form {
  margin-bottom: 20px;
}

h4 {
  font-size: xx-large;
  font-family: "Nabla", cursive;
  text-align: center;
  font-size: 2em;
}

button {
  background: #f9c132;
  padding: 10px 15px;
  color: #fff;
  cursor: pointer;
  border-radius: 20px;
  transition: transform 500ms ease;
  border: 2px solid #f9c132;
}

button:hover {
  transform: scale(1.1) translateY(-5px);
}

input {
  background-color: transparent;
  padding: 12px 18px;
  border-radius: 12px;
  border: 2px solid #f9c132;
  color: white;
  margin-right: 12px;
}
</style>
