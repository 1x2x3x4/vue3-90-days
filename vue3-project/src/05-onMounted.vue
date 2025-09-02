<script setup>
// 生命周期函数的使用
// 1.引入函数
import { onMounted } from 'vue';

// 2.执行函数 传入回调
onMounted(() => {
  console.log("组件挂载完毕mounted执行了----1")
  
})
onMounted(() => {
  console.log("组件挂载完毕mounted执行了----3")
  
})
onMounted(() => {
  console.log("组件挂载完毕mounted执行了----2")
  
})
</script>

<template>
</template>
