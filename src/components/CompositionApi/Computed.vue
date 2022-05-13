<template>
  <div>
    <input v-model="refFirstName" placeholder="First Name" type="text" />
    <input v-model="refLastName" placeholder="Last Name" type="text" />
  </div>

  <h1> The fullname is : {{ refFullName }} </h1>
</template>

<script> // import computed 
import { ref, computed } from 'vue';
export default {
  name: "Computed",
  setup(){
      const refFirstName = ref('');
      const refLastName = ref('');
      const refFullName = computed(() => {
          return `${refFirstName.value} ${refLastName.value}`
      })

            // Pareil pour reactive
        
      return {
          refFirstName,
          refLastName,
          refFullName,
      }

  },
  data() {
    return {
        
    };
  },
};
</script>

<style scoped>
</style>