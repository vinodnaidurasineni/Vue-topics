<template>
  <!-- <img :alt="show" :src="getPic" > -->
  <div id="app1">
  <a :href="google">external link</a>
  <p :class="{ boldclass : makemebold === true }">Make as bold</p>
  <input name="email" ref="email">
  <button @click="checkRef">Get Ref data</button>

  <Modal  :name="name" :test="test" :sampleArray="[1,2,3]" @inputFocus="checkRef">
    <p>i am in parent comp coming in child comp</p>
    <h1>i am header</h1>
    <template v-slot:link>
      <a href="">LInk 1</a>
      <a href="">link 2</a>
    </template>
  </Modal>
  <!-- <Modal></Modal> -->
  <!-- <input name="test" ref="input">
  <p :class="{italic: show}">i am some content </p>
  <div v-if="show">
  <HelloWorld msg="Welcome to Your Vue.js App" @closeme="checkRef"/></div>
  <button @click="checkRef">Focus on m e</button> -->
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import Modal from "./components/ModalCom.vue"

export default {
  name: 'App',
  components: {
    Modal
  },
  data(){
    return{
      makemebold: true,
      name:"I am modal component",
      test:" I  am another prop",
      // show:false,
      google:"https://google.com"
    }

  },
  methods:{
    checkRef(){
      console.log(this.$refs.email);
      this.$refs.email.focus();
      // this.show=!this.show
    }
  }
}
</script>

<style scoped>
#app1 {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.italic{
  background-color: black;
}
.boldclass{
  color: blue;
}

p{
  background-color: blue;
}
</style>
