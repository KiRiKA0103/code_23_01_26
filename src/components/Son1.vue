<template>
    <div class="son1">
        <h4>Son1</h4>
        <p>父组件传递的msg值是:{{ msg }}</p>
        <p>父组件传递的info值是:{{ user }}</p>
        <button @click="send">Son1发送至Son3</button>
    </div>
</template>

<script>
import bus from './eventBus.js'

export default {
    components: {},
    props: ['msg', 'user'],
    data() {
        return {
            str: 'Son1---->Son3'
        };
    },
    watch: {},
    computed: {},
    methods: {
        send() {
            bus.$emit('share', this.str)
        }
    },
    created() { },
    mounted() { }
};
</script>
<style lang="less">

</style>