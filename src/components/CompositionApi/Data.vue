<template>
    <div>
        <h1> Options -  {{ o_firstName }}</h1>
        <h1> Composition -  {{ greet }}</h1>
        <hr>
        <h1> {{ reactiveGreetHero }} </h1>
    </div>
</template>

<script>

import {ref, reactive} from 'vue';

//  ref avec des valeurs primitives
// reactive ne prend qu'un objet en argument (bien pour un groupe de variables allant ensemble)

    export default {
        name :'Data',
        setup(){ // point d'entrée de la Composition API
            const c_firstName = ref('Clark')
            const c_lastName = ref('Kent')
            const c_heroName = ref('Superman')
            const greet = `Hello ${c_firstName.value} ${c_lastName.value} a.k.a ${c_heroName.value} `

        const state = reactive({
            firstName: 'Bruce',
            lastName: 'Wayne',
            heroName: 'Batman',
        })

        const reactiveGreetHero = `Hello ${state.firstName} ${state.lastName} a.k.a ${state.heroName} `
            return {
                c_firstName,
                c_lastName,
                c_heroName,
                greet,
                state,
                reactiveGreetHero
            }
        },
        data() {
            return {
                o_firstName: 'Séb'
            }
        },
    }
</script>

<style scoped>

</style>