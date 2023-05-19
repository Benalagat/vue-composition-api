

<template>
  <div class="posts">
    <h1>Posts</h1>
    <ul>
      <li
        v-for= "post in posts"
          :key="post.id"
          >
        <RouterLink :to="`/postDetail/${post.id}`">{{ post.title }}</RouterLink>
        
      </li>
    </ul>
    <textarea v-autofocus/>
</div>
</template>
<script setup>
import {ref} from 'vue'
import{vAutofocus} from '@/directives/vAutofocus.js'

// const route=useRoute()
const posts=ref([
  {
    id:'id1',
    title:'post one'
  },
  {
    id:'id2',
    title:'post two'
  },
  {
    id:'id3',
    title:'post three'
  }
 ])
</script>
<style scope>
  ul{
    margin-bottom: 30px;
  }
</style>