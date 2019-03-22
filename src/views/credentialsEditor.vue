<template>
  <div>
    <h2>个人信息</h2>
    <el-form label-position="top" :model="credentials">
      <el-form-item label="姓名">
        <el-input v-model="credentials.name"></el-input>
      </el-form-item>
      <el-form-item label="出生年月">
        <el-input v-model="credentials.birth"></el-input>
      </el-form-item>
      <el-form-item label="籍贯">
        <el-input v-model="credentials.origin"></el-input>
      </el-form-item>
    </el-form>
  </div>
</template>
<script>
export default {
    props: ['credentials']
}
</script>

