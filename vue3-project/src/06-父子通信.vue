<!-- <script setup>

import sonCom from './son-com.vue';
import { ref } from 'vue';
const count = ref(100)

setTimeout(() => {
  count.value = 50000
},3000)

</script>

<template>

  <div class="father">
    <h3>父组件App</h3>
    <sonCom :count="count" message="father message"></sonCom>
  </div>

</template> -->

<script setup>
import sonCom from './06-son-com.vue';
const getMessage = (msg) => {
  console.log(msg);
  
}
</script>

<template>
  <div class="father">
    <h3>父组件App</h3>
    <!-- 1.绑定事件 -->
    <sonCom @get-message="getMessage"></sonCom>
  </div>
</template>
