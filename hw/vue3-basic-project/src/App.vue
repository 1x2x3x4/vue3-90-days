<script setup>
import { onMounted, ref } from 'vue';
import Edit from './components/Edit.vue'
import axios from 'axios';

// TODO: 列表渲染
// 思路 声明响应式list -> 调取接口获取数据 -> 将后端数据赋值给list -> 绑定table组件 
const list = ref([])
const getList =  async () => {
  const res = await axios.get('/list')
  list.value = res.data
}

onMounted(() => getList())
// TODO: 删除功能
// 获取当前行的id -> 调用删除接口 -> 在调用删除后的更新列表数据
const deleteList = async (id) => {
  // console.log(id);
  await axios.delete(`/del/${id}`)
  getList()
  
 }

// TODO: 编辑功能
// 打开窗口 -> 回填数据 -> 更新数据
// 1.打开弹窗（获取子组件实例 调用方法或者修改属性）
// 2.回调数据（调用详细接口/当前行的静态数据）
const editRef = ref(null)
const onEdit = (row) => {
  editRef.value.open(row)
}

</script>

<template>
  <div class="app">
    <el-table :data="list">
      <el-table-column label="ID" prop="id"></el-table-column>
      <el-table-column label="姓名" prop="name" width="150"></el-table-column>
      <el-table-column label="籍贯" prop="place"></el-table-column>
      <el-table-column label="操作" width="150">
        <template #default="{row}">
          <el-button type="primary" @click="onEdit(row)" link>编辑</el-button>
          <el-button type="danger" @click="deleteList(row.id)" link>删除</el-button>
        </template>
      </el-table-column>
    </el-table>
  </div>
  <Edit ref="editRef" @on-update="getList()"/>
</template>

<style scoped>
.app {
  width: 980px;
  margin: 100px auto 0;
}
</style>
