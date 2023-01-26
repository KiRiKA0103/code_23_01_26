<template>
  <div class="test-container">
    <h3 id="myh3">Test.vue 组件</h3>
    <p>{{ books.length }}本书</p>
    <p id="myp">msg 的值是 {{ msg }}</p>
    <button @click="msg += '~'">修改msg的值</button>
  </div>
</template>

<script>
export default {
  components: {},
  props: ['info'],
  data() {
    return {
      msg: 'hello vue.js',
      books: []
    }
  },
  watch: {},
  computed: {},
  methods: {
    show() {
      console.log('调用了Test的show');
    },
    initBookList() {
      const xhr = new XMLHttpRequest()
      xhr.addEventListener('load', () => {
        const result = JSON.parse(xhr.responseText)
        console.log(result)
        this.books = result.data
      })
      xhr.open('GET', 'http://www.liulongbin.top:3006/api/getbooks')
      xhr.send()
    }
  },
  // created 生命周期函数，非常常用。
  // 经常在它里面，调用 methods 中的方法，请求服务器的数据。
  // 并且，把请求到的数据，转存到 data 中，供 template 模板渲染的时候使用！
  created() {
    this.initBookList()
  },

  // 如果要操作当前组件的 DOM，最早，只能在 mounted 阶段执行
  mounted() {

    const dom = document.querySelector('#myh3')
    console.log(dom);
  },

  beforeUpdate() {
    // console.log(this.msg);
    // const dom = document.querySelector('#myp')
    // console.log(dom.innerHTML);
  },
  
  // 当数据变化之后，为了能够操作到最新的 DOM 结构，必须把代码写到 updated 生命周期函数中
  updated() {
    console.log(this.msg);
    const dom = document.querySelector('#myp')
    console.log(dom.innerHTML);
  }
};
</script>
<style lang="less">

</style>