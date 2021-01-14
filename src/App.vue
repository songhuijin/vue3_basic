<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <!-- <p>{{count}}</p>
  <p>{{double}}</p>
  <button @click="add">+1</button> -->
  <p>{{data.count}}</p>{{count}}
  <p>{{data.double}}</p>
  <button @click="data.addFun">+1</button>
</template>

<script lang="ts">
// import { ref ,computed} from 'vue'
import {reactive,computed,toRefs} from 'vue'
// interface Idata {
//   count : number;
//   addFun : ()=>{};
//   double : number; 
// }
export default({
  name: 'App',
  setup(){
    // const count = ref(1)
    // const double = computed (()=>{
    //   return count.value * 2
    // })
    // const add =()=>{
    //   count.value ++ 
    // }
    const data= reactive({
      count:0,
      addFun:()=>{
         data.count++
      },
      double:computed(()=>{
         data.count *2
      })
    })
    const refsData = toRefs(data)
    return {
      data,
      ...refsData
      // count,
      // add,
      // double
    }
  },
  
});
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
