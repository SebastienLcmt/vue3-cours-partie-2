<template>
    <div>
        <h1> {{name}} </h1>
    </div>
    <hr>
    <h1>{{ firstName }} {{ lastName }} </h1>
</template>

<script>

import { reactive, ref, toRefs } from 'vue';
 
    export default {
        name : 'DemoOne',
        setup() {
            const name = ref('Sébastien');

            setTimeout(() => {
                name.value = "Bisounours"
            }, 2000)

        const state = reactive({
            firstName: 'Bruce',
            lastName: 'Wayne',
        });

       
            return {
                ...toRefs(state),
                name,
            }
           
        }
    }
</script>

<style scoped>

</style>