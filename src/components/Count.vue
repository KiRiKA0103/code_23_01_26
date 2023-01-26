<template>
    <div class="Count-container">
        <h3>Count 组件</h3>
        <h5>count h5 标签</h5>
        <p>count={{ count }}</p>
        <button @click="count += 1">+1</button>
    </div>
</template>

<script>
export default {
    // props的值是只读的
    // props: ['init'],
    props: {
        init: {
            // 外界使用组件时没有传init属性 使用默认值
            default: 0,
            // 规定传入值的类型
            type: Number,
            // 规定属性为必传项
            required: true,
        }
    },

    data() {
        return {
            count: this.init
        }
    }
}
</script>

<style lang="less">
.Count-container {
    height: 100px;
    margin: auto;
    background-color: pink;
}
</style>


