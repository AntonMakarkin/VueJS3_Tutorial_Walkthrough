<template>
  <Greet name="Anton" surname="Makarkin"/>
  <Greet name="Vika" surname="Shipko"/>
  <Greet name="Vova" surname="Maksin"/>
  <Greet :name="name" :surname="channel"/>
</template>

<script>
import GreetComponent from './components/Greet.vue'

export default {
  name: 'App',
  components: {
    Greet: GreetComponent
  },
  data() {
    return {
      name: 'Vishwas',
      channel: 'Codevolution'
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
}
</style>
