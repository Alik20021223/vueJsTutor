<template>
  <input type="number" @input="changeAmount($event.target.value)" placeholder="Введите число"/>
</template>
<script>
export default {
  props: {
    changeAmount: {
        type: Function,
        required: true
    }
  }
}
</script>
<style scoped>
input {
  outline: none;
  width: 500px;
  text-align: center;
  border-radius: 8px;
  border: 0;
  padding: 10px 15px;
  background: #fafafa;
  color: #333;
}
</style>
