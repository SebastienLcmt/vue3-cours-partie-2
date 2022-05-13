<template>
    <div>
        <input v-model="firstName" type="text" />
        <input v-model="lastName" type="text" />
    </div>
        <PropsChild :firstName="firstName" :lastName="lastName" @alert="alertFromChild"/>
</template>

<script>

    import { ref } from 'vue';
    import PropsChild from './PropsChild.vue'

    export default {
        name: 'Props',
         components: {
            PropsChild,
        },
        setup() {
            const firstName = ref('');
            const lastName = ref('');

            function alertFromChild(fullNameFromChild){
                alert(`Alerte depuis l'enfant avec nom ${fullNameFromChild}`)
            }

            return {
                firstName,
                lastName,
                alertFromChild
            }
        },
       
    }
</script>

<style lang="scss" scoped>

</style>