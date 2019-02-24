<template>
  <div class="chat-composer">
     <input type="text" placeholder="Add message" v-model="messageText" @keydown.enter="sendMessage">
     <button class="btn btn-primary" @click="sendMessage">Send</button>
  </div>
</template>

<script>
export default {
  data(){
    return {
      messageText: ''
    }
  },
  props: ['user_name'],
  methods: {
    sendMessage(){
      this.$emit('messagesent', {
        message: this.messageText,
        user: {
          name: "You"
        },
      });
      this.messageText = '';
    }
  }
}
</script>

<style lang="css" scoped>
.chat-composer {
  display: flex;
}
.chat-composer input{
  flex:1 auto;
}

</style>
