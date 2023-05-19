

<template>
  <div class="home">
    <h2>{{ appTitle }}</h2>
    <h3>{{ counterData.title }}</h3>
    <div>
    <button @click="decreaseCounter(2)" class="btn">--</button>
    <button @click="decreaseCounter(1)" class="btn">-</button>
    <span class="counter">{{ counterData.count }}</span>
    <button @click="increaseCounter(1)" class="btn">+</button>
    <button @click="increaseCounter(2)" class="btn">++</button>
    </div>
    <p>This counter is {{ oddOrEven }}</p>
    <div class="edit">
      <h4>Edit counter title</h4>
      <input v-model="counterData.title" type="text" v-autofocus/>
    </div>
</div>
</template>

<script setup>
import {reactive,computed, watch} from 'vue'
import{vAutofocus} from '@/directives/vAutofocus.js'

const appTitle='My  first counter app'
const counterData=reactive({
  count:0,
  title:'My Counter'
})
watch(()=>counterData.count, (newCount)=>{
  if(newCount==20) alert('20 count reached')
})
const oddOrEven=computed(()=>{
  if(counterData.count%2===0)return 'even'
  return 'odd'
})
const increaseCounter=amount=>{
  counterData.count+=amount
}
const decreaseCounter=amount=>{
  counterData.count-=amount
}

</script>
<!-- <script>
export default{
  data(){
    return{
      count:0
    }
  },
  computed:{
    myComputedProperty(){
      return 'My result'
    }
  },
  watch:{
    count(newCount,oldCount){
      if(newCount==20) alert('20 count reached')
    }
  }, 
  mounted(){
    console.log('mounted')
  },
  unmounted(){
    console.log('unmounted')
  }
}
</script> -->



<style>
.head{
  text-align: center;
  padding: 20px;
}
.btn, .counter{
  font-size: 40px;
  margin: 10px;
}
.edit{
  margin-top:60px;
}
</style>