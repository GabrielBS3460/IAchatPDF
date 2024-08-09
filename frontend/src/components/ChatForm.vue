<template>
  <b-container class="chat-form">
    <b-form @submit.prevent="sendMessage">
      <b-form-group label="Envie Sua Pergunta:" label-for="message">
        <b-form-input
            id="message"
            v-model="message"
            required
        ></b-form-input>
      </b-form-group>
      <b-button class="mt-2" type="submit" variant="primary">Send</b-button>
    </b-form>
    <b-alert class="mt-2" v-model="isResponse" dismissible @dismissed="isResponse = false">
      <p style="white-space: pre-wrap">{{ response }}</p>
    </b-alert>
  </b-container>
</template>

<script>
import axios from 'axios';
import {BButton, BContainer, BForm, BFormGroup, BFormInput, BAlert} from "bootstrap-vue-next";

export default {
  name: 'ChatForm',
  components: {BButton, BFormInput, BFormGroup, BForm, BContainer, BAlert},
  data() {
    return {
      message: '',
      response: null,
      isResponse: false
    };
  },
  methods: {
    async sendMessage() {
      try {
        const res = await axios.post('/api/chat', this.message);
        this.response = res.data;
        this.isResponse = true;
        console.log(this.response);
      } catch (error) {
        console.error('Error sending message:', error);
      }
    }
  }
}
</script>

<style scoped>
.chat-form {
  max-width: 600px;
  margin: 2rem auto;
}


</style>
