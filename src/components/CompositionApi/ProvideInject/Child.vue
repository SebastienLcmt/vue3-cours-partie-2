<template>
  <div>
    {{ childUsername }}
  </div>
  <h2>{{ childCount }}</h2>
  <h2> {{firstName}} {{ lastName }}</h2>
  <button @click="incrementCount">increment</button>
</template>

<script>
import { inject, toRefs } from "vue";
export default {
  name: "Child",
  // inject: ['name'],

  setup() {
    const childUsername = inject("c_username", "default value");
    const childCount = inject("c_count");
    const childHero = inject("c_hero");
    
    const incrementCount = inject('incrementCount')

    return {
      childUsername,
      childCount,
      incrementCount,
      ...toRefs(childHero),
    };
  },
};
</script>

<style scoped>
</style>