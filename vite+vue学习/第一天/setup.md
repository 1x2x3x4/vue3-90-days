使用语法糖前：

```js
<script>
export default {
  setup() {
    console.log("setup");
    const message = "this is message"
    const logmessage = () => {
      console.log(message);
    }
    return {
      message,
      logmessage,
    }
  },
  beforeCreate() {
    console.log("beforeCreate");
  }
}
</script>
<template>
  <div>{{message}}</div>
  <button @click="logmessage">log</button>
</template>
```





使用语法糖后：

```javascript
<script setup>
console.log("setup");
const message = "this is message"
const logmessage = () => {
  console.log(message);
}
</script>
<script setup>
console.log("setup");
const message = "this is message"
const logmessage = () => {
  console.log(message);
}
</script>
<template>
  <div>{{message}}</div>
  <button @click="logmessage">log</button>
</template>
```





结论：可以节约大量重复性工作，但是代码在底层运行的时候还是原先的代码