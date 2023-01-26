<template>
    <div class="Son3">
        <h4>Son3</h4>
        <p>{{ strFromSon1 }}</p>
    </div>
</template>

<script>
import bus from './eventBus.js'

export default {
    components: {

    },
    props: {},
    data() {
        return {
            strFromSon1: ''
        };
    },
    watch: {},
    computed: {},
    methods: {},
    created() {
        bus.$on('share', (val) => {
            console.log('接收到Son1传来的信息');
            this.strFromSon1 = val
        })
    },
    mounted() { }
};
</script>
<style lang="less">

</style>