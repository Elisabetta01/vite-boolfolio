<script >

import axios from 'axios';

export default{
  data(){
    return{
      posts: []
    }
  },

  mounted(){
    this.getPosts()
  },

  methods: {
    getPosts(){
      axios.get('http://127.0.0.1:8000/api/posts')
        .then( res => {
          this.posts = res.data.posts
          console.log(res.data)
        })
    }
  },
}

</script>

<template>
  <h1>Ciao mondo</h1>
</template>

<style lang="scss">
@use './style/main.scss';
</style>
