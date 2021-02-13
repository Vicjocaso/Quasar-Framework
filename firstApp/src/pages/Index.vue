<template>
  <q-page padding>
    <input v-model="message"
    @keyup.esc="clearMessage"
    @keyup.enter="alertMessage">
    <button @click="clearMessage()">Click</button>
    <h1 class="border-grey" v-show="message.length"> {{message}} </h1>
  </q-page>
</template>

<script>
export default {
  data () {
    return {
      message: 'Quasar is fun '
    }
  },
  methods: {
    clearMessage () {
      this.message = ''
    },
    alertMessage () {
      alert(this.message)
    }
  }
}
</script>
<style>
 .border-grey {
   border: 1px solid grey;
 }

</style>
