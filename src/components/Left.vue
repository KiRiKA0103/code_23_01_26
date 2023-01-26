<template>
  <div class="left-container">
    <h3>Left 组件</h3>
    <hr>
    <MyCount :init="5"></MyCount>
  </div>
</template>

<script>
export default {}
</script>

<style lang="less" scoped>
.left-container {
  padding: 0 20px 20px;
  background-color: orange;
  min-height: 250px;
  flex: 1;

  h3 {
    color: red;
  }

  // 使用第三方组件库时候 如果有修改第三方组件默认样式的需求 需要用的/deep/
  /deep/ h5 {
    color: blue;
  }
}
</style>
<style lang="less">
h3 {
  font-size: 30px;
}
</style>
