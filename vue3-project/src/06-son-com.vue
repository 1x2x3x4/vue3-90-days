<!-- <script setup>


const props = defineProps({
    message: String,
    count:Number
})
console.log(props);


</script>

<template>
    <div class="son">
        <h2>子组件Son</h2>
        {{ message }}----{{ count }}
    </div>

</template> -->

<script setup>
// 2.通过defineEmits() -> emit(this.$emit)
const emit = defineEmits(['get-message'])

const sendmessage = () => {
    // 触发自定义事件，传数据给父组件
    emit('get-message','this is son message')
}

</script>

<template>
 <div class="son">
        <div>子组件son</div>
        <button @click="sendmessage">触发自定义事件</button>
 </div>
</template>