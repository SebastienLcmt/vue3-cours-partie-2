<template>
    <div>
        <input type="text" ref="inputRef" />
    </div>
</template>

<script>

    // Pas de lifecycles hook created et beforeCreate dans la composition API.
    // Les noms changent : mounted() => onMounted(),  update() => onUpdate(), etc...

import { onMounted, ref } from 'vue';

    export default {
        name : 'LifecycleHooks',

        setup(){

            const inputRef = ref(null);

            onMounted(() => {
                inputRef.value.focus()
            });

            return {
                inputRef,
            }
        }

    }


</script>

<style scoped>

</style>