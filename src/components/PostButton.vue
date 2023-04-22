<template>
    <div>
        <button @click="post_notify">POST</button>
    </div>
</template>

<script>
    export default {
        methods: {
            post_notify: function () {
                let message = `Successfully posted!`;
                this.$root.$emit(`post_toast_notify`, message);
            }
        }
    }
</script>

<style scoped>

</style>