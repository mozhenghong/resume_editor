<template>
  <div>
    <h2>联系方式</h2>
    <el-form label-position="top" :model="contact">
      <el-form-item label="电话">
        <el-input v-model="contact.phone"></el-input>
      </el-form-item>
      <el-form-item label="邮箱">
        <el-input v-model="contact.email"></el-input>
      </el-form-item>
    </el-form>
  </div>
</template>
<script>
export default {
    props: ['contact']
}
</script>