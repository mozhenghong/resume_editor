<template>
  <div id="Preview">
    <section class="credentials">
      <h2>个人信息</h2>
      <p>{{resume.credentials.name||'请填写姓名'}} | {{resume.credentials.birth||'请填写出生年月'}} | {{resume.credentials.origin||'请填写籍贯'}}</p>
    </section>
    <section class="workHistory" v-if="filter(resume.workHistory)">
      <h2>工作经历</h2>
      <ul>
          <li v-for="work in resume.workHistory">
             
          </li>
      </ul>
    </section>
  </div>
</template>

<script>
export default {
  props: ["resume"],
  methods: {
      filter(arr){
          return arr.filter((item) => { !this.isEmpty(item)})
      },
      isEmpty(object){
          let empty = true
          for(let key in object){
              if(object[key]){
                  empty = false
                  break
              }
              
          }
      },
      
  }
};
</script>

<style>
#Preview {
}
</style>
