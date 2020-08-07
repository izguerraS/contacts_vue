<template>
  <div class="home">
    <button v-on:click="indexContacts()">Get Contacts</button><div v-for='contact in contacts'>
    <h1>{{ message }}</h1>
    <h1>{{ contacts }}</h1>
  </div>
</div>
</template>

<style>
</style>

<script>
import axios from 'axios';
export default {
  data: function() {
    return {
      message: "Welcome to Vue.js!",
      contacts: [],
    };
  },
  created: function() {},
  methods: {
    indexContacts: function () {
      console.log('contact indexing...');
      axios.get('api/contacts').then(response => {
        console.log(response);
        this.contacts = response.data;
      })
    }
  }
};
</script>