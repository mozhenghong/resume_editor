<template>
  <div id="Editor">
    <nav>
      <ol>
        <li
          v-for="i in [0,1,2,3,4,5]"
          v-bind:class="{active:currentTag===i}"
          v-on:click="currentTag=i"
        >
          <svg class="icon" aria-hidden="true">
            <use v-bind:xlink:href="`#icon-${icons[i]}`"></use>
          </svg>
        </li>
      </ol>
    </nav>
    <ol class="list">
      <li v-bind:class="{active:currentTag===0}" class="credentials">
        <h2>个人信息</h2>
        <el-form :label-position="labelPosition" :model="credentials">
          <el-form-item label="姓名">
            <el-input v-model="credentials.name"></el-input>
          </el-form-item>
          <el-form-item label="出生年月">
            <el-input v-model="credentials.birth"></el-input>
          </el-form-item>
          <el-form-item label="籍贯">
            <el-input v-model="credentials.origin"></el-input>
          </el-form-item>
          <el-button type="primary">保存</el-button>
          <el-button>取消</el-button>
        </el-form>
      </li>
      <li v-bind:class="{active:currentTag===1}">
        <h2>工作经历</h2>
        <el-form :label-position="labelPosition" v-for="(work, index) in workHistory" class="break">
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
      </li>
      <li v-bind:class="{active:currentTag===2}">
         <h2>教育背景</h2>
      </li>
      <li v-bind:class="{active:currentTag===3}">
         <h2>项目经验</h2>
      </li>
      <li v-bind:class="{active:currentTag===4}"> 
        <h2>职业技能</h2>
      </li>
       <li v-bind:class="{active:currentTag===5}"> 
        <h2>联系方式</h2>
      </li>
    </ol>
  </div>
</template>

<script>
export default {
  data() {
    return {
      currentTag: 0,
      icons: [
        "credentials_icon",
        "WORK",
        "xuexi",
        "xiangmu",
        "jineng",
        "dianhua"
      ],
      labelPosition: "right",
      credentials: {
        name: "",
        birth: "",
        origin: "",
      },
      workHistory:[
        {date: '', company:'', content: ''}
      ]
    };
  },
  methods:{
    addWorkHistory(){
      this.workHistory.push({date: '', company:'', content: ''})
    },
    removeWorkHistory(index){
      console.log(1)
      this.workHistory.splice(index, 1)
    }
  }
};
</script>

<style lang="scss">
#Editor {
  display: flex;
  background: #fff;
  nav {
    background: #254665;
    ol {
      margin: 16px 0;
      li {
        padding: 16px;
        .icon {
          width: 35px;
          height: 35px;
          fill: #fff;
        }
      }
      li.active {
        background: #fff;
        .icon {
          fill: #254665;
        }
      }
    }
  }
  ol.list {
    flex-grow: 1;
    overflow: auto;
    li {
      display: none;
      padding: 25px;
      .break{
      border-bottom:1px solid  #254665;
      margin-bottom: 10px;
      position: relative;
        .remove{
          position: absolute;
          right: 0;
          top: 0;
          z-index: 1;
          color: #254665;
        }
      }
    }
    li.active {
      display: block;
    }
  }
}
</style>


