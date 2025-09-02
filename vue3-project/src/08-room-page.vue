<script setup>
import { provide, ref } from 'vue';
import RoomMsgItem from './08-room-msg-comment.vue'

// 1.传递数据
provide('data-key','this is room data')

const count = ref(100)
// 顶层组件提供响应式数据
provide('count-key', count)

setTimeout(() => {
    count.value=300
}, 3000)

// 传递方法(谁的数据谁负责修改)
const setcount = () => {
    count.value++
}
provide('setcount-key',setcount)

</script>


<template>

<div class="page">
    <div>顶层组件</div>
    <RoomMsgItem></RoomMsgItem>
</div>
  
</template>