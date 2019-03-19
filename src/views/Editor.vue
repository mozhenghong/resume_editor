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
          <el-form-item label="手机">
            <el-input v-model="credentials.phone"></el-input>
          </el-form-item>
           <el-form-item label="邮箱">
            <el-input v-model="credentials.email"></el-input>
          </el-form-item>
          <el-button type="primary">保存</el-button>
          <el-button>取消</el-button>
        </el-form>
      </li>
      <li v-bind:class="{active:currentTag===1}">
       
      </li>
      <li v-bind:class="{active:currentTag===2}">tab3</li>
      <li v-bind:class="{active:currentTag===3}">tab4</li>
      <li v-bind:class="{active:currentTag===4}">tab5</li>
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
        phone: "",
        email: ""
      }
    };
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
    }
    li.active {
      display: block;
    }
  }
}
</style>


