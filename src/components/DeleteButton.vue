<template>
    <div>
        <button @click="delete_notify">DELETE</button>
    </div>
</template>

<script>
    export default {
    methods: {
        delete_notify: function() {
            let message = `Successfully deleted!`;
            this.$root.$emit(`delete_toast_notify`, message);
        }
    }
    }
</script>

<style scoped>

</style>