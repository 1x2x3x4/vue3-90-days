<script setup>
import { ref } from 'vue';
import { computed } from 'vue';
const list = ref([1, 2, 3, 4, 5, 6, 7, 8])

const computedList = computed(() => {
  return list.value.filter(item=>item>2)
})

setTimeout(() => {
  list.value.push(9,10,11)
},3000)
</script>

<template>
<div>原来的数组-{{list}}</div>
<div>现在的数组-{{computedList}}</div>
</template>