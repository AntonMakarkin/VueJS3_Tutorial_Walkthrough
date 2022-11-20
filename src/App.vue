<template>
<!--<Greet name="Anton" surname="Makarkin"/>
  <Greet name="Vika" surname="Shipko"/>
  <Greet name="Vova" surname="Maksin"/>
  <Greet :name="name" :surname="channel"/>

  <Article id="my-article" title="Article Title" :likes="50" :isPublished="true"/>
  -->
  <h3>AppComponent username {{ name }}</h3>
  <ComponentC/>

  <button @click="showPopup = true">Show Popup</button>
  <Popup v-show="showPopup" @close="closePopup"/>
</template>

<script>
//import GreetComponent from './components/Greet.vue';
//import Article from './components/Article.vue'
import ComponentC from './components/ComponentC'
import Popup from './components/Popup.vue'

export default {
  name: 'App',
  components: {
    ComponentC,
    Popup
    //Greet: GreetComponent,
    //Article
  },
  data() {
    return {
      name: 'Anton',
      showPopup: false
    }
  },
  provide() {
    return {
      username: this.name
    }
  },
  methods: {
    closePopup(name) {
      this.showPopup = false
      console.log('name', name)
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
