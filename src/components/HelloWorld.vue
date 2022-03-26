<template>
  <div class="hello">
    <el-table :data="tableData"
              border
              style="width: 100%">
      <el-table-column prop="date"
                       label="Date"
                       width="180" />
      <el-table-column prop="name"
                       label="Name"
                       width="180" />
      <el-table-column prop="address"
                       label="Address" />
      <el-table-column fixed="right"
                       label="Operations"
                       width="120">
        <template #default="scope">
          <el-button type="text"
                     size="small"
                     @click="handleClick(scope.$index)">删除</el-button>

        </template>
      </el-table-column>
    </el-table>
  </div>
</template>

<script>
import {
  defineComponent,
  toRefs,
  reactive
} from 'vue'
export default defineComponent({
  name: 'HelloWorld',
  setup () {
    const state = reactive({
      tableData: [
        {
          date: '2016-05-03',
          name: 'Tom',
          address: 'No. 189, Grove St, Los Angeles',
        },
        {
          date: '2016-05-02',
          name: 'Tom',
          address: 'No. 189, Grove St, Los Angeles',
        },
        {
          date: '2016-05-04',
          name: 'Tom',
          address: 'No. 189, Grove St, Los Angeles',
        },
        {
          date: '2016-05-01',
          name: 'Tom',
          address: 'No. 189, Grove St, Los Angeles',
        }]
    })
    const handleClick = (index) => state.tableData.splice(index, 1)
    return {
      ...toRefs(state),
      handleClick
    }
  }
})
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
