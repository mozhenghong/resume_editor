<template>
  <div>
    <h2>职业技能</h2>
    <el-form label-position="top" v-for="(item, index) in skills" class="break">
      <i class="el-icon-error remove" v-on:click="removeSkills(index)"></i>
      <el-form-item label="技能">
        <el-input v-model="item.content"></el-input>
      </el-form-item>
    </el-form>
    <el-button type="primary" v-on:click="addSkills">添加</el-button>
  </div>
</template>
<script>
export default {
    props: ['skills'],
    methods:{
    addSkills(){
      this.skills.push({content: ''})
    },
    removeSkills(index){
      this.skills.splice(index, 1)
    }
  },
}
</script>
