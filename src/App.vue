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

  <Input v-model="appName"/>
  
  <Card>Card content</Card>
  <Card>
    <h2>Card content</h2>
  </Card>
  <Card>
    <img src="https://picsum.photos/200"/>
  </Card>

  <Card>
    <template v-slot:header>
      <h3>Header</h3>
    </template>
    <template v-slot:default>
      <img src="https://picsum.photos/200"/>
    </template>
    <template v-slot:footer>
      <button>View Details</button>
    </template>
  </Card>

  <NameList>
    <template v-slot:default="slotProps">
      {{ slotProps.firstName }} {{ slotProps.lastName }}
    </template>
  </NameList>
  <NameList>
    <template v-slot:default="slotProps">
      {{ slotProps.lastName }} {{ slotProps.firstName }}
    </template>
  </NameList>

  <h4>App component text</h4>
  <ChildStyles>
    <h4>Childstyles component text</h4>
  </ChildStyles>

  <button @click="activeTab = 'TabA'">Tab A</button>
  <button @click="activeTab='TabB'">Tab B</button>
  <button @click="activeTab='TabC'">Tab C</button>

  <keep-alive>
    <component :is="activeTab"/>
  </keep-alive>

  <!--<TabA v-if="activeTab === 'TabA'"/>
  <TabB v-if="activeTab === 'TabB'"/>
  <TabC v-if="activeTab === 'TabC'"/>-->
  <teleport to='#portal-root'>
    <Portal/>
  </teleport>
</template>

<script>
//import GreetComponent from './components/Greet.vue';
//import Article from './components/Article.vue'
import ComponentC from './components/ComponentC'
import Popup from './components/Popup.vue'
import Input from './components/Input.vue'
import Card from './components/Card.vue'
import NameList from './components/NameList.vue'
import ChildStyles from './components/ChildStyles.vue'

import TabA from './components/TabA.vue';
import TabB from './components/TabB.vue';
import TabC from './components/TabC.vue';

import Portal from './components/Portal.vue';

export default {
  name: 'App',
  components: {
    ComponentC,
    Popup,
    Input,
    Card,
    NameList,
    ChildStyles,
    TabA,
    TabB,
    TabC,
    Portal
    //Greet: GreetComponent,
    //Article
  },
  data() {
    return {
      name: 'Anton',
      appName: '',
      showPopup: false,
      activeTab: 'TabA'
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

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h4 {
  color: orange
}
</style>
