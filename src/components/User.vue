<template>
  <div class="user">
    <button @click="deleteUser(index)">Удалить</button>
    <h3>{{ user.name }}</h3>
    <p>
      {{ user.email }} - <b>{{ user.password }}</b>
    </p>

  </div>
</template>

<script>
export default {
  name: 'UserItem',
  props: {
    user: {
        type: Object,
        required: true
    },
    index: {
        type: Number,
        required: true
    },
    deleteUser: {
        type: Function,
        required: true,
    }
  } // Multi-word component name
}
</script>

<style scoped>

button {
    border: 2px solid #0a0a0a;
    border-radius: 5px;
    outline: none;
    padding: 10px 15px;
}

.user {
  /* Add styles for the user component */
  margin: 10px;
  padding: 10px;
  border: 2px solid #0a0a0a;
  border-radius: 8px;
}
</style>
