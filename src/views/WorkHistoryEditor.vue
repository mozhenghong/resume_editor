<template>
  <div>
    <h2>工作经历</h2>
    <el-form label-position="top" v-for="(work, index) in workHistory" class="break">
      <i class="el-icon-error remove" v-on:click="removeWorkHistory(index)"></i>
      <el-form-item label="起止时间">
        <el-input v-model="work.date"></el-input>
      </el-form-item>
      <el-form-item label="公司名称">
        <el-input v-model="work.company"></el-input>
      </el-form-item>
      <el-form-item label="工作内容">
        <el-input v-model="work.content"></el-input>
      </el-form-item>
    </el-form>
    <el-button type="primary" v-on:click="addWorkHistory">添加</el-button>
  </div>
</template>
<script>
export default {
    props: ['workHistory'],
    methods:{
    addWorkHistory(){
      this.workHistory.push({date: '', company:'', content: ''})
    },
    removeWorkHistory(index){
      this.workHistory.splice(index, 1)
    }
  },
}
</script>
