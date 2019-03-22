<template>
  <div>
    <h2>项目经验</h2>
    <el-form label-position="top" v-for="(item, index) in project" class="break" v-bind:key="index">
      <i class="el-icon-error remove" v-on:click="removeProject(index)"></i>
      <el-form-item label="起止时间">
        <el-input v-model="item.duration"></el-input>
      </el-form-item>
      <el-form-item label="项目名称">
        <el-input v-model="item.name"></el-input>
      </el-form-item>
      <el-form-item label="项目内容">
        <el-input v-model="item.content"></el-input>
      </el-form-item>
    </el-form>
    <el-button type="primary" v-on:click="addProject">添加</el-button>
  </div>
</template>
<script>
export default {
    props: ['project'],
    methods:{
    addProject(){
      this.project.push({ name: '', duration:'', content: ''})
    },
    removeProject(index){
      this.project.splice(index, 1)
    }
  },
}
</script>
