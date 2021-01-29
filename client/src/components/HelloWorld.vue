<template>
  <div class="hello">
    <div class="posts">
      <div
        v-for="post in allPosts"
        :key="post._id"
        class="post"
      >
        {{ post.text }}
      </div>
    </div>
  </div>
</template>

<script>
import { mapGetters, mapActions } from "vuex";

export default {
  name: 'HelloWorld',
  methods: {
    ...mapActions(["fetchPosts"])
  },
  computed: mapGetters(["allPosts"]),
  created() {
    this.fetchPosts();
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
