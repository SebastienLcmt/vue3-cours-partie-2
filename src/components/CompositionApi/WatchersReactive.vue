<template>
  <div>
    <input v-model="firstName" type="text" placeholder="firstname" />
    <input v-model="lastName" type="text" placeholder="lastname" />
    <input v-model="options.heroName" type="text" placeholder="heroname" />
  </div>
</template>

<script>
import { reactive, toRefs, watch } from "vue";
export default {
  name: "WatchersReactive",
  setup() {
    const state = reactive({
        firstName: '',
        lastName: '',
        options: {
            heroName: '',
        }
    });
    //  Ici on watch toutes les propriétés de state
    // watch(() => {
    //     return {...state}    /// d'abord return copy de la variable car valeur de référence
    // }, (newValue, oldValue) => {
    //     console.log(oldValue.firstName);
    //     console.log(newValue.firstName);
    //     console.log(oldValue.lastName);
    //     console.log(newValue.lastName);
    // });

    // Pour ne watch qu'une seule propriété
    watch(() => state.firstName, (newValue, oldValue) => {
        console.log(oldValue);
        console.log(newValue);
    })


    return {
        ...toRefs(state)
    }
  },
};
</script>

<style scoped>
</style>