<template>
  <div id="memberCentre">
    <div class="top">
      <el-button class="addBtn" type="primary">添加会员</el-button>
      <div class="searchBox">
        <el-input placeholder="请输入内容"></el-input>
        <el-button type="primary">搜索</el-button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
}
</script>

<style lang="scss">
#memberCentre {
  padding: 10px;
  .top {
    position: relative;
    .addBtn {
      float: left;
    }
    .searchBox {
      float: right;
    }
  
  }
}
</style>
