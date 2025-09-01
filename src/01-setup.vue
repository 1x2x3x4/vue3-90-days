<!-- <script>
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
</script> -->
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