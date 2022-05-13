<template>
    <!--  Watchers with REF only in this example -->
  <div>
    <input v-model="firstName" type="text" placeholder="firstname" />
    <input v-model="lastName" type="text" placeholder="lastname" />
  </div>
</template>

<script>
import { ref, watch } from "vue";
export default {
  name: "Watchers",
  setup() {
    const firstName = ref("");
    const lastName = ref("wayne");

    // trois arguments : variable to watch (ou tableau de variable), fonction prenant new et old valeurs, et enfin un objet pour spécifier si le watch doit être fait immédiatement 

    watch([firstName, lastName], (newValues, oldValues) => {
      console.log(newValues[0]);
      console.log(oldValues[0]);
      console.log(newValues[1]);
      console.log(oldValues[1]);
    }, {
        immediate: true,
    });

    return {
      firstName,
      lastName
    };
  },
};
</script>

<style scoped>
</style>