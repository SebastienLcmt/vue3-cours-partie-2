<template>
  <div>
    <button @click="incrementCount">Button clicked {{ count }} times</button>
  </div>
</template>

<script>
import CounterMixin from "../mixins/counter";
// Pour réutiliser du code utilisé dans plein de composants différents

export default {
  name: "Mixins",
  mixins : [CounterMixin],
  data() {
      return {
          name: 'salut',
      }
  },
};
</script>

<style scoped>
button {
  padding: 20px;
  font-size: 17px;
}
</style>