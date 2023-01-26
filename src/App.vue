<template>
  <div class="app-container">
    <h1>App 根组件</h1>
    <hr />
    <Test info="hello world"></Test>
    

    <div class="box">
      <!-- 渲染 Left 组件和 Right 组件 -->
      <Left></Left>
      <Right></Right>
    </div>

    <br><br><br><br><br>
    <hr>
    <Father></Father>
  </div>
</template>

<script>
import Left from '@/components/Left.vue'
import Right from '@/components/Right.vue'
import Test from '@/components/Test.vue'
import Father from '@/components/Father.vue'


export default {
  data() {
    return {

    }
  },
  components: {
    Left,
    Right,
    Test,
    Father
  }
}
</script>

<style lang="less">
.app-container {
  padding: 1px 20px 20px;
  background-color: #efefef;
}
.box {
  display: flex;
}
</style>
