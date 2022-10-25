<template>
    <div class="message-box" v-if="message">
        <div>Title : {{message.title}}</div>
        <div>Content : {{message.content}}</div>
        <div>Date : {{message.date.toLocaleDateString()}}</div>
    </div>
</template>

<script>
    export default {
        name: "MessageDetail",
        props: {
            message: null
        },
    }
</script>

<style scoped>
    .message-box {
        display: flex;
        flex-direction: column;
    }
</style>