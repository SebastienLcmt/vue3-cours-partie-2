<template>
    <div>
        <h1> {{ count }} </h1>
        <button @click="increment"> increment </button>
    </div>
    <div>
        <h1> {{ firstName }} {{ lastName }} </h1>
        <button @click="changeHero">Change Hero</button>

    </div>
</template>

<script>
import { ref, reactive, toRefs } from "vue";
    export default {
        name: 'Methods',
        data() {
            return {
                
            }
        },
        setup() {
            const count = ref(0);
            const state = reactive({
                firstName: 'Bruce',
                lastName: 'Wayne'
            })

           function increment(){
               count.value++;
           }

           function changeHero(){
               state.firstName = 'Clark'
               state.lastName = 'Kent'
           }

            return {
                count, 
                increment,
                changeHero,
                ...toRefs(state)
            }
        }
    }
</script>

<style scoped>

</style>