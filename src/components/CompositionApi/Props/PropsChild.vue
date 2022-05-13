<template>
    <div>
        <h1> {{ fullName }} </h1>
        <button @click="sendEvent"> Alert from Child </button>
    </div>
</template>

<script>

    import  { computed }  from 'vue';

    export default {
        name: 'PropsChild',
        setup(props, context) {

            const fullName = computed(() => {
                return `${props.firstName}  ${props.lastName}`
            })

            function sendEvent(){
                context.emit('alert', fullName.value)
            }

            return {
                fullName,
                sendEvent,
            }
        },
       props: ['firstName', 'lastName'] // important
    }
</script>

<style scoped>

</style>