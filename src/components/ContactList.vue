<template>
  <div>
    <ul v-if="hasContacts">
      <li v-for="contact in contactNames" v-bind:key="contact">{{ contact }}</li>
    </ul>
    <p v-else>Contact list is empty :(</p>
  </div>
</template>

<script>
export default {
  props: {
    contacts: {
      required: true,
      default: () => []
    }
  },
  computed: {
    contactNames() {
      return this.contacts.map((c) => c.name)
    },
    hasContacts() {
      return this.contacts.length > 0
    }
  },
}
</script>

<style>

</style>