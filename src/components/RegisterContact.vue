<template>
  <form v-on:submit.prevent="registerContact">
    <input type="text" placeholder="Name" v-model="inputName" />
    <input type="text" placeholder="Phone" v-model="inputPhone" />
    <input type="text" placeholder="Email" v-model="inputEmail" />
    <button type="submit">Cadastrar</button>
  </form>
</template>

<script>
export default {
  data: () => ({
    inputName: '',
    inputPhone: '',
    inputEmail: '',
  }),
  methods: {
    registerContact() {
      this.$emit('register', {
        name: this.inputName,
        phone: this.inputPhone,
        email: this.inputEmail
      })

      this.inputName = ''
      this.inputPhone = ''
      this.inputEmail = ''
    }
  }
}
</script>

<style>

</style>