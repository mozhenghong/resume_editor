<template>
  <div id="app">
    <Topbar class="Topbar" v-on:preview="preview" v-bind:class="{preview:isPreview}"></Topbar>
    <main>
      <Editor class="Editor" v-bind:resume="resume" v-bind:class="{preview:isPreview}"></Editor>
      <Preview class="Preview" v-bind:resume="resume"></Preview>
      <el-row class="buttons">
        <el-button
          class="button"
          type="primary"
          v-on:click="exitPreview"
          v-bind:class="{exitPreview:!isPreview}"
        >取消预览</el-button>
      </el-row>
    </main>
  </div>
</template>

<script>
import Topbar from "./views/Topbar";
import Editor from "./views/Editor";
import Preview from "./views/Preview";
export default {
  components: {
    Topbar,
    Editor,
    Preview
  },
  data() {
    return {
      resume: {
        credentials: {
          name: "",
          birth: "",
          origin: ""
        },
        workHistory: [{ date: "", company: "", content: "" }],
        educationHistory: [{ date: "", school: "", degree: "" }],
        project: [{ name: "", duration: "", content: "" }],
        skills: [{ content: "" }],
        contact: { phone: "", email: "" }
      },
      isPreview: false
    };
  },
  methods: {
    preview() {
      this.isPreview = true;
    },
    exitPreview() {
      this.isPreview = false;
    }
  }
};
</script>

<style lang="scss">
.icon {
  width: 1em;
  height: 1em;
  vertical-align: -0.15em;
  fill: currentColor;
  overflow: hidden;
}
#app {
  height: 100vh;
  display: flex;
  flex-direction: column;
  .preview {
    display: none;
  }
  main {
    display: flex;
    flex-grow: 1;
    background: #00c091;
    .preview {
      display: none;
    }
    .Editor {
      width: 40vw;
      box-shadow: 0 3px 5px 0 rgba(0, 0, 0, 0.1);
      background-color: #fff;
      margin: 16px 8px 16px 16px;
      border-radius: 4px;
      overflow: hidden;
    }
    .Preview {
      flex-grow: 1;
      box-shadow: 0 3px 5px 0 rgba(0, 0, 0, 0.1);
      background-color: #fff;
      margin: 16px 16px 16px 8px;
      border-radius: 4px;
      overflow: hidden;
    }
    .buttons {
      position: relative;
      .exitPreview{
        display: none;
      }
      .button{
        position: absolute;
        bottom: 30px;
        right: 30px;
        z-index: 10;
        padding: 8px 16px;
        background-color: #00c091;
        border-color: #00c091;
      }
    }
  }
}
</style>