<template>
  <h1>Crypto</h1>
  <Nigga :changeAmount="changeAmount"/>
  <div class="selectors">
    <Selector />
    <Selector />
  </div>
  {{ amount }}
</template>
<script>
import Nigga from "./components/Input.vue";
import Selector from "./components/Selector.vue";
export default {
  components: { Nigga, Selector },
  data () {
    return {
      amount: 0,
      cryptoFirst: ''
    }
  },
  methods: {
    changeAmount(value) {
      this.amount = value;
    }
  }
};
</script>
<style>
.selectors {
  display: flex;
  width: 500px;
  justify-content: space-around;
  margin: 40px auto;
}
</style>
