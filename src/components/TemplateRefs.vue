<template>
  <div>
    <input type="text" ref="inputRef" />
  </div>
  <PostList ref="postListRef"/>
</template>

<script>
import PostList from "./PostList.vue";


export default {
  name: "TemplateRefs",
  mounted() {
    console.log(this.$refs.postListRef); // ref est le composant en entier
    this.$refs.inputRef.focus(); // ref est l'input
  },
  components: {
      PostList,
  }
};
</script>

<style scoped>
</style>