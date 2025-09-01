<!-- <script setup>

import { ref, watch } from 'vue'
const count = ref(0)

const setcount = () => {
  count.value++;
}
watch(count, (newVal,oldVal) => {
  console.log('count变化了',oldVal,newVal);
  
})
</script>

<template>
<div><button @click="setcount">+{{ count }}</button></div>
</template> -->

<!-- <script setup>
import { ref, watch } from 'vue'
const count = ref(0)
const name = ref("cp")
const setcount = () => {
  count.value++;
}
const changename = () => {
  name.value = "pc";
}
watch(
  [count, name],
  ([newcount, newname], [oldcount, oldname]) => {
    console.log("count或者name变化了",[newcount, newname], [oldcount, oldname]);
    
  }
)
</script>

<template>
<div><button @click="setcount">修改了count----{{ count }}</button></div>
<div><button @click="changename">修改了name----{{ name }}</button></div>
</template> -->

<!-- <script setup>
import { ref, watch } from 'vue';

const state = ref({count:0})

const setcount = () => {
  state.value.count++
}
watch(state, () => {
  console.log("count变化了");
  
}, {
  deep:true
})

</script>

<template>
  {{state.count}}
<div><button @click="setcount">count---</button></div>
</template> -->

<!-- <script setup>
import { ref, watch } from 'vue';

const state = ref({
  name: "chaichai",
  age:18
})

const changename = () => {
  state.value.name = "chaichai-teacher"
}
const changeage = () => {
  state.value.age = 20
}
watch(
  () => state.value.age,
  ()=>{console.log("age被修改了");}
)

</script>

<template>
<div>{{state.name}}</div>
<div>{{ state.age }}</div>

<div><button @click="changename">修改name</button></div>
<div><button @click="changeage">修改age</button></div>

</template> -->
