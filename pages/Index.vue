<template>
  <el-container class="Index">
    <el-header>This is header</el-header>
    <el-main class="main">现在时间为：{{date}}</el-main>
    <el-footer height="30">This is Footer</el-footer>
  </el-container>
</template>
<script>
const haha = require("../js/haha.ts");
export default {
  data() {
    return {
      date: haha.getTime()
    };
  },
  methods: {}
};
</script>
<style lang="less">
@import url("../common.less");
.Index {
  width: 100%;
  height: 100%;
  @header-height: 60px;
  @footer-height: 30px;
  @header-footer-height: @header-height+ @footer-height;
  @header-background-color: #49188a;
  .el-header {
    height: @header-height;
    background-color: @header-background-color;
    color: white;
    display: flex;
    align-items: center;
  }

  .el-footer {
    height: @footer-height;
    background: #333333;
    color: #aaaaaa;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .el-main {
    height: calc(~"100% - " @header-footer-height);
  }
}
</style>
