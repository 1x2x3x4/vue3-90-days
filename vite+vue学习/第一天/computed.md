定义：接收一个参数，响应式返回计算值

```javascript
import {computed} from 'vue'
const computedState = computed(()=>{
	return 基于响应式数据计算之后的值
})
```



应用：

```javascript
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
```

filter方法：

```javascript
筛选数组里面的
item=>item>2
等价写法：
function(item) {
  return item > 2
}
/*
item：传进来的每一个元素（list 里的一项）。

item > 2：判断它是不是大于 2。

return item > 2：把判断的结果（true 或 false）返回。
*/
```







