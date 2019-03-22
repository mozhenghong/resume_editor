<template>
  <div id="Preview">
    <section class="credentials">
      <h2>{{resume.credentials.name||'请填写姓名'}}</h2>
      <p> {{resume.credentials.birth||'请填写出生年月'}} | {{resume.credentials.origin||'请填写籍贯'}}</p>
    </section>
    <section class="workHistory">
      <h2>工作经历</h2>
      <hr>
      <ul>
          <li v-for="(work, key) in resume.workHistory" v-bind:key="key">
             {{work.date||'请填写工作经历'}} {{work.company}}  {{work.content}}
          </li>
      </ul>
    </section>
    <section class="educationHistory">
      <h2>教育背景</h2>
      <ul>
          <li v-for="(item, key) in resume.educationHistory" v-bind:key="key">
             {{item.date||'请填写教育背景'}} {{item.school}}  {{item.degree}}
          </li>
      </ul>
    </section>
    <section class="project">
      <h2>项目经验</h2>
      <ul>
          <li v-for="(item, key) in resume.project" v-bind:key="key">
             {{item.duration||'请填写项目经验'}} {{item.name}}  {{item.content}}
          </li>
      </ul>
    </section>
     <section class="skills">
      <h2>职业技能</h2>
      <ul>
          <li v-for="(item, key) in resume.skills" v-bind:key="key">
             {{item.content||'请填写职业技能'}} 
          </li>
      </ul>
    </section>
     <section class="contact">
      <h2>联系方式</h2>
      <p>电话:{{resume.contact.phone||'请填写电话'}}</p>
      <p>邮箱:{{resume.contact.email||'请填写邮箱'}}</p>
    </section>
  </div>
</template>

<script>
export default {
  props: ["resume"],
  methods: {
      filter(array){
          return array.filter((item) => { !this.isEmpty(item)})
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
