<template>
  <div>
    <input v-model="fName" placeholder="First Name" type="text" />
    <input v-model="lName" placeholder="Last Name" type="text" />
  </div>
  <hr />
  <div>
    <input v-model="heroName" placeholder="Hero Name" type="text" />
    <input v-model="firstName" placeholder="First Name" type="text" />
    <input v-model="lastName" placeholder="Last Name" type="text" />
  </div>
</template>

<script>
import { ref, reactive, toRefs } from "vue";

export default {
  name: "VModel",

  setup() {
    const heroName = ref("");
    const state = reactive({
      firstName: "",
      lastName: "",
    });

    return {
      heroName,
      ...toRefs(state),
    };
  },

  data() {
    return {
      fName: "",
      lName: "",
    };
  },
};
</script>

<style scoped>
</style>