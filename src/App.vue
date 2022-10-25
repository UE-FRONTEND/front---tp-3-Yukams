<template>
  <div>
    <div class="col">
      <new-message @messageSubmit="storeMessage"/>
    </div>
    <div class="col">
      <message-preview :messages="messages" @selectMessage="seeMessageDetails"></message-preview>
    </div>
    <div class="col">
      <message-detail :message="selected"></message-detail>
    </div>
  </div>
</template>

<script>
import NewMessage from "./components/NewMessage";
import MessagePreview from "./components/MessagePreview";
import MessageDetail from "./components/MessageDetail";

export default {
  name: 'App',
  components: {
    NewMessage,
    MessagePreview,
    MessageDetail
  },
  data: function () {
    return {
      messages: [],
      selected: null
    }
  },
  methods: {
    storeMessage(message) {
      this.messages.push(
        {
          title: message.title,
          content: message.content,
          id: this.messages.length,
          date: new Date(),
          isRead: false
        }
      )
    },
    seeMessageDetails(message) {
      message.isRead = true
      this.selected = message;
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.col {
  width: 30%;
  display: inline-block;
  margin: 5px;
  vertical-align: top;
}
</style>
