<template>
  <q-page padding>
    <button @click="counter++">
      {{ counter }}
    </button>
    <input v-model="message"
    @keyup.esc="clearMessage"
    @keyup.enter="alertMessage"
    v-autofocus
    :class="{ 'error' : message.length > 22 }"
    ref="messageInput">
    <button @click="clearMessage()">Click</button>
    <h1 class="border-grey" v-if="message.length"> {{message}} {{message.length}} </h1>

    <h4 v-else>No Mesannge Entered</h4>

    <hr>
    <p >Uppercase message: {{ messageUppercase }}</p>
    <p>Lowercase message: {{ message | messageLowercase }} </p>
  </q-page>
</template>

<script>
export default {
  data () {
    return {
      message: 'Quasar is fun ',
      counter: 0
    }
  },
  computed: {
    messageUppercase () {
      return this.message.toUpperCase() + this.counter
    }
  },
  methods: {
    clearMessage () {
      this.message = ''
    },
    alertMessage () {
      alert(this.message)
    }
  },
  filters: {
    messageLowercase (value) {
      return value.toLowerCase()
    }
  },
  directives: {
    autofocus: {
      inserted (el) {
        el.focus()
      }
    }
  },
  mounted () {
    console.log(this.$refs)
    this.$refs.messageInput.className = 'bg-green'
  }
}
</script>
<style>
 .border-grey {
   border: 1px solid grey;
 }
 input, bottom {
   font-size: 23px;
 }
 .error {
   color: red;
   background: pink;
    }

</style>
