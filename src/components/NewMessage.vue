<template>
  <div class="box box-style">
    <div class="new-message-title">
      Nouveau Message
    </div>
    <div class="message-title-box box-padding">
      <input class="message-title box-style" v-model="message.title"/>
    </div>
    <div class="message-content-box box-padding">
      <textarea class="message-content box-style" v-model="message.content"></textarea>
    </div>
    <div class="message-button-box">
      <button class="submit-button" @click="onClick()">Soumettre</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "NewMessage",
  data: function () {
    return {
      message: {
        title: "",
        content: ""
      }
    }
  },
  methods: {
    onClick() {
      this.$emit('messageSubmit', this.message);
      this.message.title = "";
      this.message.content = "";
    }
  }
}
</script>

<style scoped>
  .box-style {
    display: flex;
    flex-direction: column;
    border-radius: 4px;
    border-style: solid;
    border-width: 1px;
    border-color: lightgrey;
  }

  .box {
    width: 300px;
    min-height: 200px;
  }

  .new-message-title {
    height: 50px;
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-weight: bold;
  }

  .box-padding {
    padding: 10px 20px;
  }

  .message-title-box {
    height: 50px;
    width: 100%;
  }

  .message-button-box {
    height: 50px;
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    padding-bottom: 10px;
  }

  .submit-button {
    background-color: dodgerblue;
    border-radius: 4px;
    border-style: solid;
    border-width: 1px;
    border-color: lightgrey;
    color: white;
    padding: 5px 10px;
  }

  .message-content-box, .message-content, .message-title {
    height: 100%;
    width: 100%;
  }
</style>