<template>
    <div class="father">
        <h3>Father----{{ countFromSon }}</h3>
        <Son1 :msg="msg" :user="info"></Son1>
        <Son2 @numchange="getNewCount"></Son2>
        <Son3></Son3>

    </div>
</template>

<script>

import Son1 from '@/components/Son1.vue'
import Son2 from '@/components/Son2.vue'
import Son3 from '@/components/Son3.vue'

export default {
    components: {
        Son1,
        Son2,
        Son3,
    },
    props: {

    },
    data() {
        return {
            msg: 'hello world',
            info: {
                id: 1,
                account: 'akari',
                pwd: '123456'
            },
            countFromSon:0
        };
    },
    watch: {},
    computed: {},
    methods: {
        getNewCount(val) {
            this.countFromSon = val
        }
    },
    created() { },
    mounted() { }
};
</script>
<style lang="less">

</style>