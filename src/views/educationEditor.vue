<template>
  <div>
    <h2>教育背景</h2>
    <el-form label-position="top" v-for="(item, index) in educationHistory" class="break" v-bind:key="index">
      <i class="el-icon-error remove" v-on:click="removeEducationHistory(index)"></i>
      <el-form-item label="起止时间">
        <el-input v-model="item.date"></el-input>
      </el-form-item>
      <el-form-item label="学校名称">
        <el-input v-model="item.school"></el-input>
      </el-form-item>
      <el-form-item label="学位">
        <el-input v-model="item.degree"></el-input>
      </el-form-item>
    </el-form>
    <el-button type="primary" v-on:click="addEducationHistory">添加</el-button>
  </div>
</template>
<script>
export default {
    props: ['educationHistory'],
    methods:{
    addEducationHistory(){
      this.educationHistory.push({date: '', school:'', degree: ''})
    },
    removeEducationHistory(index){
      this.educationHistory.splice(index, 1)
    }
  },
}
</script>
