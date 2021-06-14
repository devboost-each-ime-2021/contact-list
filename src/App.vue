<template>
  <div id="app">
    <h1>Agenda</h1>
    <div class="app-container">
      <RegisterContact v-on:register="addNewContact" />
      <ContactList v-bind:contacts="contacts" />
    </div>
  </div>
</template>

<script>
import RegisterContact from '@/components/RegisterContact.vue'
import ContactList from '@/components/ContactList.vue'

export default {
  name: 'App',
  components: {
    RegisterContact,
    ContactList,
  },
  data: () => ({
    contacts: []
  }),
  methods: {
    addNewContact(contact) {
      this.contacts.push(contact)
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
  display: flex;
  flex-direction: column;
  align-items: center;
}

.app-container {
  display: flex;
  width: 70%;
  justify-content: center;
}

.app-container form {
  display: flex;
  flex-direction: column;
}
</style>
