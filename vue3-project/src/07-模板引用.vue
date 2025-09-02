<script setup>
import testCom from './07-test-com.vue';
import { onMounted, ref } from 'vue';

// 赋值给变量 h2Ref -> 创建响应式对象
const h2Ref = ref(null)
const testComRef = ref(null)
//获取模板引用的前提条件是挂载完毕
onMounted(() => {
  console.log(h2Ref.value);
  console.log(testComRef.value);
  
  
})

</script>

<template>
<h1>这是父组件</h1>
<h2 ref="h2Ref">我是dom标签</h2>
<testCom ref="testComRef"></testCom>
</template>