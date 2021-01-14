<template>
  {{count}}{{double}}
  <button @click="add">+1</button>
</template>

<script lang="ts">
import { ref ,computed} from 'vue'
export default({
  name: 'refAPI',
  setup(){
    const count = ref(1)
    const double = computed (()=>{
      return count.value * 2
    })
    const add =()=>{
      count.value ++ 
    }

    return {
      count,
      add,
      double
    }
  },
  
});
</script>

<style>

</style>
