<script>

import axios from 'axios';

    export default{
        name: "ProjectCard",
        data() {
            return {
               posts: [],
               baseUrl: 'http://127.0.0.1:8000/api',
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
       <div class="container">
          <div class="row">
               <div class="col-6" v-for="(element, index) in posts" :key="index">
                    <div class="card">
                      <img class="card-img-top" :src="`${baseUrl}/storage/${element.img}`" alt="Title">
                      <div class="card-body">
                        <h4 class="card-title">{{element.title}}</h4>
                        <p class="card-text">{{element.description}}</p>
                      </div>
                    </div>
               </div>
          </div>
        </div>
        
</template>

<style lang="scss" scoped>

</style>
