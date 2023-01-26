<template>
    <div class="Son2">
        <h4>Son2----{{ count }}</h4>
        <button @click="add">+1</button>
    </div>
</template>

<script>
export default {
    components: {},
    props: {},
    data() {
        return {
            count:0
        };
    },
    watch: {},
    computed: {},
    methods: {
        add() {
            this.count += 1
            this.$emit('numchange',this.count)
        }
    },
    created() { },
    mounted() { }
};
</script>
<style lang="less">

</style>