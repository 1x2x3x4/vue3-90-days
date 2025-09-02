<script setup>
import { inject } from 'vue';

    // 2.接收数据
    const roomdata = inject('data-key')
    // 底层组件接收响应式数据
    const countdata = inject('count-key')

    const setcount = inject('setcount-key')

</script>


<template>
<div class="commet">
    <div>
        底层组件
    </div>
    <div>
        来自顶层组件的数据：{{ roomdata }}
    </div>
    <div>
        来自顶层组件的响应式数据：{{ countdata }}
    </div>
    <div>
        <button @click="setcount">点击按钮修改顶层组件的count</button>
    </div>
</div>
  
</template>