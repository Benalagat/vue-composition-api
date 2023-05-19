

<template>
    <div class="post-detail">
      <h1>This is a post page</h1>
      <p>Display the post with the Id of{{ $route.params.id }} here!</p>
      <div>
        <button @click='showPostId'>Show Id</button>
      </div>
      <div>
        <button @click="goHomeIn3Seconds">Go Home In 3 Seconds</button>
      </div>
  </div>
  </template>
 <script setup>
 
 import{useRoute,useRouter} from 'vue-router'

 const route=useRoute()
 const router=useRouter()
 const showPostId=()=>{
  alert(`The id of this post is: ${route.params.id }`)
 }

 const goHomeIn3Seconds=()=>{
  setTimeout(()=>{
    router.push({name:'home'})
  },3000)
 }
</script>