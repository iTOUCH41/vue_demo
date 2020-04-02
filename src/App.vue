<template>
  <div id="app">
    <h1>WELCOME</h1>
    <h1>TO</h1>
    <h1>iTOUCH</h1>
    <h1>what is your name:{{message}}</h1>
    <input v-model="message" :placeholder="name" type="text" >
    <button @click="show" >SUBMIT</button>
    <h1 v-if="isShow">{{ renderName() }}</h1>
    <ul>
      <li>Books 101</li>
      <li v-for="book in books" :key="book.id"> {{ renderName(book.book_name) }} <a :href="book.book_link_text">TEXT</a></li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      message:"",
      isShow: false,
      name: "Please enter your name",
      array: [1,2,3,4,5,6,7,8,9,0],
      books: [
        {
          "id": 1,
          "book_name": "พ่อสอนลูก",
          "book_link_pdf": "http://book.rgtcenter.com/004-01.pdf",
          "book_link_text": "http://book.rgtcenter.com/004-01.txt"
        },
      ]
    }
  },
  computed: {
    phraName () {
      let randomChaya = Math.random()
      let chayaArray = ["....."]

      let resultChaya = chayaArray[Math.floor(randomChaya * chayaArray.length)]
      return `พระมหา${this.message} ${resultChaya}`
    }
  },
  methods: {
    show () {
      return this.isShow = !this.isShow //toggle
    }, 
    renderName (name) {
      return `Hello ${name}!`
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
