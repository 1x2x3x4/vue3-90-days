<script setup>
// TODO: 编辑
import { ref } from 'vue'
import axios from 'axios'
// 弹框开关
const from = ref({
  name: "",
  place: "",
  id:""
})
const dialogVisible = ref(false)
const emit = defineEmits(['on-update'])

const open = (row) => {
  dialogVisible.value = true
  // console.log(row);
  from.value.name = row.name
  from.value.place = row.place
  from.value.id = row.id
  
}

defineExpose({
  open
})
//更新
const onUpdate = async (row) => {
  // 1.收集表单数据 调用接口
  await axios.patch(`/edit/${from.value.id}`, {
  name: from.value.name,
  place: from.value.place,
  })
  // 2.关闭弹框
  dialogVisible.value = false
  // 3.通知父组件做列表更新
  emit('on-update')
 
}

</script>

<template>
  <el-dialog v-model="dialogVisible" title="编辑" width="400px">
    <el-form label-width="50px">
      <el-form-item label="姓名">
        <el-input placeholder="请输入姓名" v-model="from.name"/>
      </el-form-item>
      <el-form-item label="籍贯">
        <el-input placeholder="请输入籍贯" v-model="from.place" />
      </el-form-item>
    </el-form>
    <template #footer>
      <span class="dialog-footer">
        <el-button @click="dialogVisible = false">取消</el-button>
        <el-button type="primary" @click="onUpdate">确认</el-button>
      </span>
    </template>
  </el-dialog>
</template>

<style scoped>
.el-input {
  width: 290px;
}
</style>
