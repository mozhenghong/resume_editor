<template>
  <div id="Topbar">
    <svg class="icon" aria-hidden="true">
      <use xlink:href="#icon-resume"></use>
    </svg>
    <el-row class="buttons">
      <el-button class="button1" type="primary" v-on:click="preview">预览</el-button>
    </el-row>
  </div>
</template>

<script>
export default {
  methods: {
    preview() {
      this.$emit('preview')
    }
  }
};
</script>

<style lang="scss">
#Topbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 16px;
  box-shadow: 0 3px 5px 0 rgba(0, 0, 0, 0.1);
  position: relative;
  z-index: 1;
  .icon {
    width: 30px;
    height: 30px;
    fill: #00c091;
  }
  .buttons {
    .button1 {
      padding: 8px 16px;
      background-color: #00c091;
      border-color: #00c091;
    }
  }
}
</style>


