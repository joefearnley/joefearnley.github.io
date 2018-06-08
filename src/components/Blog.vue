<template>
  <div>
    <div
      v-for="post in posts" 
      :key="post.id">
  </div>
</template>

<script>
export default {
  name: 'Blog',
  data () {
    return {
      posts: []
    }
  },
  methods: {
    getPosts: function() {
      return [{
      },
      {

      }];
    }
  }
}
</script>