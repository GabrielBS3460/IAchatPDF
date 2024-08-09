<template>
  <div id="app">
      <Navbar />
      <ChatForm />
  </div>
</template>

<script>
import Navbar from './components/NavbarComponent.vue';
import ChatForm from './components/ChatForm.vue';

export default {
  name: 'App',
  components: {
    Navbar,
    ChatForm
  }
}
</script>

<style>
body {
  font-family: Arial, sans-serif;
  background-color: #f8f9fa;
  margin: 0;
  padding: 0;
}
</style>
