<template>
  <div id="app">
    <Topbar class="Topbar"></Topbar>
    <main>
      <Editor class="Editor"></Editor>
      <Preview class="Preview"></Preview>
    </main>
  </div>
</template>

<script>
import Topbar from './views/Topbar';
import Editor from './views/Editor';
import Preview from './views/Preview';
export default {
  components: {
    Topbar,
    Editor,
    Preview,
  }  
}
</script>

<style lang="scss">
.icon {
  width: 1em; height: 1em;
  vertical-align: -0.15em;
  fill: currentColor;
  overflow: hidden;
}
#app{
  height: 100vh;
  display: flex;
  flex-direction: column;
  main{
    display: flex;
    flex-grow: 1.0;
    background: #00C091;
    .Editor{
      width: 40vw;
      box-shadow: 0 3px 5px 0 rgba(0, 0, 0, 0.1);
      background-color: #fff;
      margin: 16px 8px 16px 16px;
      border-radius: 4px;
      overflow: hidden;
    }
    .Preview{
      flex-grow: 1.0;
      box-shadow: 0 3px 5px 0 rgba(0, 0, 0, 0.1);
      background-color: #fff;
      margin: 16px 16px 16px 8px;
      border-radius: 4px;
      overflow: hidden;
    }
  }
}
</style>