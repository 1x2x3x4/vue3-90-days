<script setup>

// import { reactive } from 'vue'
// const state = reactive({
//   count:0
// })
// const countAdd = () => {
//   state.count++;
// }
import {ref} from 'vue'

const count = ref(0)
console.log(count);

const setcount = ()=> {
  count.value++;
}


</script>

<template>
  <div >
    <button @click="setcount">{{ count }}</button>
  </div>
</template>