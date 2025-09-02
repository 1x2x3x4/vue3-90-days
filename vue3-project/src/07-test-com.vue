<script setup>
import { ref } from 'vue';


const name = ref("test name")

const setname = () => {
    name.value = "test new name"
}
// 显示暴露组件内部的属性和方法（vue3里面原本是关闭的）
defineExpose({
    name,
    setname
})

</script>

<template>
    <h1>这是test页面</h1>
  
</template>