<template>
    <!-- <button @click="getPosts">Load Posts</button> -->
    <div v-for="post in posts" :key="post.id">
        <h3> {{ post.title }} </h3>
        <p> {{ post.body }} </p>
        <hr>
    </div>
</template>

<script>

import axios from 'axios';

    export default {
        name: 'PostList',
        created() { // quand le composant est créé, on appelle l'Api
            this.getPosts()
        },
        data() {
            return {
                posts: [],
            }
        },
        methods: {
            async getPosts(){
                await axios.get('https://jsonplaceholder.typicode.com/posts')
                .then((response) => { // response déjà parsée avec axios
                   this.posts = response.data;
                })
                .catch((err) => {
                    console.log(err);
                })
                
            }
        },
        components: {
            
        }
    }
</script>

<style scoped>

button {
    width : auto;
    height: 40px;
    font-size: 20px;
    padding: 10px 20px;
}

</style>