<template>
  <div>
    <form @submit.prevent="createPost">
      <div>
        <label for="userId">User Id</label>
        <input v-model="userId" id="userId" type="text" />
      </div>
      <div>
        <label for="title">Title</label>
        <input v-model="title" id="title" type="text" />
      </div>
      <div>
        <label for="body">Body</label>
        <input v-model="body" id="body" type="text" />
      </div>
      <button>Create post</button>
    </form>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "CreatePost",
  data() {
    return {
      formData: {
        userId: "",
        title: "",
        body: "",
      },
    };
  },
  methods: {
    createPost() {
      axios.post('https://jsonplaceholder.typicode.com/posts', this.formData)
      .then( response => console.log(response))
      .catch(error => console.log(error));
    },
  },
};
</script>

<style scoped>
div {
  margin: 20px;
}

input {
  margin-left: 10px;
}
</style>