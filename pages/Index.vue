<template>
  <el-container class="Index">
    <el-header>
      This is header
    </el-header>
    <el-main class="main">
      this is main
    </el-main>
    <el-footer height="30">This is Footer</el-footer>
  </el-container>
</template>
<script>  
export default {
  data() {
    return {
    };
  },
  methods: {
  }
};
</script>
<style lang="less">
@import url("../common.less");

.Index {
  .fillParent();
  .myFrame();
}
</style>
