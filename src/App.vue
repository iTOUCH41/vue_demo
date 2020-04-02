<template>
  <div id="app">
    <h1>WELCOME</h1>
    <h1>TO</h1>
    <h1>iTOUCH</h1>
    <h1>what is your name:{{message}}</h1>
    <input v-model="message" placeholder="name" type="text" >
    <button v-on:click="isHidden = !isHidden" >SUBMIT</button>
    <h1 v-if="!isHidden">Hello {{message}}!</h1>
      
  </div>
</template>

<script>
export default {
    data() {
      return {
        message:"",
        isHidden: true
      }
    },
methods: {
  show: function () {
    return this.message
  }
},
  }

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
