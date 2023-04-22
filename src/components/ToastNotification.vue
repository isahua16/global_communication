<template>
    <div>
        <p>{{delete_toast_message}}</p>
        <p>{{post_toast_message}}</p>
        <button @click="dismiss_delete_notification" v-if="delete_toast_message !== undefined">Dismiss Delete</button>
        <button @click="dismiss_post_notification" v-if="post_toast_message !== undefined">Dismiss Post</button>
    </div>
</template>

<script>
    export default {
        methods: {
            show_delete_toast: function (message) {
                this.delete_toast_message = message;
            },
            dismiss_delete_notification: function () {
                this.delete_toast_message = undefined;
            },
            show_post_toast: function (message) {
                this.post_toast_message = message;
            },
            dismiss_post_notification: function () {
                this.post_toast_message = undefined;
            }
        },  
        mounted () {
            this.$root.$on(`delete_toast_notify`, this.show_delete_toast);
            this.$root.$on(`post_toast_notify`, this.show_post_toast)
        },
        data() {
            return {
                delete_toast_message: undefined,
                post_toast_message: undefined
            }
        },
    }
</script>

<style scoped>

</style>