<template>
<!--<Greet name="Anton" surname="Makarkin"/>
  <Greet name="Vika" surname="Shipko"/>
  <Greet name="Vova" surname="Maksin"/>
  <Greet :name="name" :surname="channel"/>

  <Article id="my-article" title="Article Title" :likes="50" :isPublished="true"/>
  -->
  <h3>AppComponent username {{ name }}</h3>
  <ComponentC/>
</template>

<script>
//import GreetComponent from './components/Greet.vue';
//import Article from './components/Article.vue'
import ComponentC from './components/ComponentC'

export default {
  name: 'App',
  components: {
    ComponentC
    //Greet: GreetComponent,
    //Article
  },
  data() {
    return {
      name: 'Anton'
    }
  },
  provide() {
    return {
      username: this.name
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
