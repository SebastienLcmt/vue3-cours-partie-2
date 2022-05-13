<template>
    <div>

    </div>
</template>

<script>

    /* 
        Vue components can go through 4 phases
         - Creation  - beforeCreate(), created()
         - Mounting // composant mounted dans le Virtual DOM - beforeMount(), mounted()
         - Updating  - data change, component rerenders - beforeUpdate(), updated()
         - Unmounting - About to be removed from the DOM - beforeUnmount(), unmounted()

        Imaginons un composant parent et un composant child. Etapes :
        1. Parent beforeCreate()
        2. Parent created()
        3. Parent beforeMount()
        4. Child beforeCreate()
        5. Child created()
        6. Child beforeMount()
        7. Child mounted()
        8. Parent mounted()

        Si on supprime le composant Child. Etapes : 
        1. Parent beforeUpdate()
        2. Child beforeUnmount()
        3. Child unmounted()
        4. Parent updated()



         Hooks moins utilisés :
         - activated() / deactivated() - pour les composants dynamiques. activated est appelé quand un composant kept-alive est activé

         - errorCaptured() - quand une erreur d'un composant descendant est capturée

         - renderTracked() / renderTriggered() - pour débogage. Pour savoir pourquoi un composant a été re-rendered par exemple
    
    */





    export default {
        name : 'ComponentLifecycleHooks',

    }
</script>

<style scoped>

</style>