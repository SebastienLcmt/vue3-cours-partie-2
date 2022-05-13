<template>
    <div>
        <Child />
    </div>
    
</template>

<script>
import Child from './Child.vue';
import {provide, ref , reactive} from 'vue';


    export default {
    name : 'ProvideInject',
    setup() {
        provide('c_username', 'Bernard') // nom de la variable que l'on envoie, valeur que l'on envoie
        
        const count = ref(0);

        function increment() {
            count.value++;
        }

        const state = reactive({
            firstName : 'Bruce',
            lastName : 'Wayne'
        })

        provide('c_count', count);
        provide('c_hero', state)
        provide('incrementCount', increment)

    return {
        count,
        increment,
    }

    },
    // data() {
    //     return {
    //         name : 'Sébastien'
    //     }
    // },
    // provide() {
    //     return {
    //         name : this.name,
    //     }
    // },
    components: { Child },
    }
</script>

<style scoped>

</style>