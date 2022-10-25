<template>
    <div v-for="message in messages">
        <hr>
        <div class="message-box">
            <div>{{message.date.toLocaleDateString()}}</div>
            <div :class="message.isRead ? '' : 'bold'">{{message.title}}</div>
            <div>
                <button @click="message.isRead = true">Voir</button>
            </div>
        </div>
    </div>
    <div class="total-messages">
        Total : {{messagesLength}}
    </div>
</template>

<script>
    export default {
        name: "MessagePreview",
        props: {
            messages: null
        },
        computed: {
            messagesLength() {
                return this.messages.length
            }
        }
    }
</script>

<style scoped>
    .message-box {
        display: flex;
        justify-content: space-around;
    }

    .total-messages {
        display: flex;
        justify-content: center;
    }

    .bold {
        font-weight: bold;
    }
</style>