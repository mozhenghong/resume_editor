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
#app{
  height: 100vh;
  display: flex;
  flex-direction: column;
  main{
    display: flex;
    flex-grow: 1.0;
    .Editor{
      width: 40vw;
    }
    .Preview{
      flex-grow: 1.0;
    }
  }
}
</style>
