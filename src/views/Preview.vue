<template>
  <div id="Preview">
    <div class="top">
      <div class="top1"></div>
      <div class="top2"></div>
    </div>
    <section class="credentials">
      <div class="title">{{resume.credentials.name||'请填写姓名'}}</div>
      <p>{{resume.credentials.birth||'请填写出生年月'}} | {{resume.credentials.origin||'请填写籍贯'}}</p>
    </section>
    <section class="workHistory">
      <div class="title">
        <svg class="icon" aria-hidden="true">
          <use v-bind:xlink:href="`#icon-WORK`"></use>
        </svg>
        <span>工作经历</span>
      </div>
      <ul>
        <li v-for="(work, key) in resume.workHistory" v-bind:key="key">
          <div>
            <b>起止时间:</b>
            {{work.date}}
          </div>
          <div>
            <b>公司名称:</b>
            {{work.company}}
          </div>
          <div>
            <b>工作内容:</b>
            {{work.content}}
          </div>
        </li>
      </ul>
    </section>
    <section class="educationHistory">
      <div class="title">
        <svg class="icon" aria-hidden="true">
          <use v-bind:xlink:href="`#icon-xuexi`"></use>
        </svg>
        <span>教育背景</span>
      </div>
      <ul>
        <li v-for="(item, key) in resume.educationHistory" v-bind:key="key">
          <div>
            <b>起止时间:</b>
            {{item.date}}
          </div>
          <div>
            <b>学校名称:</b>
            {{item.school}}
          </div>
          <div>
            <b>获得学位:</b>
            {{item.degree}}
          </div>
        </li>
      </ul>
    </section>
    <section class="project">
      <div class="title">
        <svg class="icon" aria-hidden="true">
          <use v-bind:xlink:href="`#icon-xiangmu`"></use>
        </svg>
        <span>项目经验</span>
      </div>
      <ul>
        <li v-for="(item, key) in resume.project" v-bind:key="key">
          <div>
            <b>起止时间:</b>
            {{item.duration}}
          </div>
          <div>
            <b>项目名称:</b>
            {{item.name}}
          </div>
          <div>
            <b>项目内容:</b>
            {{item.content}}
          </div>
        </li>
      </ul>
    </section>
    <section class="skills">
      <div class="title">
        <svg class="icon" aria-hidden="true">
          <use v-bind:xlink:href="`#icon-jineng`"></use>
        </svg>
        <span>职业技能</span>
      </div>
      <ul>
        <li v-for="(item, key) in resume.skills" v-bind:key="key">{{item.content||'请填写职业技能'}}</li>
      </ul>
    </section>
    <section class="contact">
      <div class="title">
        <svg class="icon" aria-hidden="true">
          <use v-bind:xlink:href="`#icon-dianhua`"></use>
        </svg>
        <span>联系方式</span>
      </div>
      <ul>
        <li>
          <b>电话:</b>
          {{resume.contact.phone||'请填写电话'}}
        </li>
        <li>
          <b>邮箱:</b>
          {{resume.contact.email||'请填写邮箱'}}
        </li>
      </ul>
    </section>
  </div>
</template>

<script>
export default {
  props: ["resume"],
  methods: {
    filter(array) {
      return array.filter(item => {
        !this.isEmpty(item);
      });
    },
    isEmpty(object) {
      let empty = true;
      for (let key in object) {
        if (object[key]) {
          empty = false;
          break;
        }
      }
    }
  }
};
</script>

<style lang="scss">
#Preview {
  overflow: auto;
  padding: 10px 0;
  .top {
    display: flex;
    height: 30px;
    margin-top: 20px;
    .top1 {
      width: 10vw;
      margin-right: 1vw;
      background-color: #254665;
      box-shadow: 0 3px 5px 0 rgba(0, 0, 0, 0.1);
    }
    .top2 {
      width: 89vw;
      background-color: #254665;
      box-shadow: 0 3px 5px 0 rgba(0, 0, 0, 0.1);
    }
  }
  section {
    padding: 0 40px;
    .title {
      color: #254665;
      padding: 20px 0;
      font-size: 24px;
      font-weight: bold;
    }
    p {
      color: #b4b4b4;
    }
    ul{
        margin-left: 40px;
    }
    li {
      color: #b4b4b4;
      padding-bottom: 8px;
    }
  }
}
</style>
