<template>
  <div>{{ greet }} {{ name }}</div>
  <div v-text="channel"></div>
  <div v-html="channel"></div>
  <h2 v-bind:id="headingId">Heading</h2>
  <button v-bind:disabled="isDisabled"> Bind</button>
  <h2 class="underline">Underlined text</h2>
  <h2 class="underline" v-bind:class="status">Status</h2>
  <h2 v-bind:class="isPromoted && 'promoted'">Promoted Movie</h2>
  <h2 v-bind:class="isSoldout ? 'sold-out' : 'new'">Soldout? movie</h2>
  <h2 v-bind:class="['new', 'promoted']">Newly promoted movie</h2>
  <h2 v-bind:class="[isPromoted && 'promoted', isSoldout ? 'sold-out' : 'new']">Array conditional movie</h2>
  <h2 v-bind:class="{
    promoted: isPromoted,
    new: !isSoldout,
    'sold-out': isSoldout
  }">Object conditional movie</h2>

  <h2 v-bind:style="{
    color: highlightColor,
    'font-size': '54px',
    'font-size': headerSize + 'px',
    paddingTop: '20px'
  }">Inline Style</h2>

  <h2 v-bind:style="headerStyleObject">Styled Object</h2>

  <div v-bind:style="[baseStyleObject, successStyleObject]">Success style</div>
  <div v-bind:style="[baseStyleObject, dangerStyleObject]">Danger style</div>

  <h2 v-if="num === 0">The number is zero</h2>
  <h2 v-else-if="num < 0">The number is negative</h2>
  <h2 v-else-if="num > 0">The number is positive</h2>
  <h2 v-else>Not a number</h2>

  <template v-if="display">
    <h2>Anton</h2>
    <h2>Codevolution</h2>
    <h2>Vue</h2>
  </template>

  <h2 v-show="showElement">Using v-show</h2>
  <h2 v-if="showElement">Using v-if</h2>  <!--if false - doesnt exist in DOM-->

  <h2 v-for="(name, index) in names" :key="name">{{ index }} {{ name }}</h2>
  <h2 v-for="(name, index) in fullnames" :key="index">{{name.first}} {{name.last}}</h2>

  <div v-for="(actor, index) in actors" :key="index">
    <h2>{{actor.name}}</h2>
    <h3 v-for="(movie, index) in actor.movies" :key="index">{{ movie }}</h3>
  </div>

  <h2 v-for="(value, key, index) in myInfo" :key="index">{{ key }} {{ value }}</h2>

  <template v-for="name in names" :key="name">
    <h2>{{name}}</h2>
    <hr>
  </template>

  <template>
    <template v-for="name in names" :key="name">
      <h2 v-if="name === 'Vika'">{{ name }}</h2>
    </template>
  </template>

  <h2>Add method - {{ add(2, 3, 5) }}</h2>
  <h2>Add method - {{ add(10, 15, 20) }}</h2>
  <h2>Multipl method - {{ multiply(10) }}</h2>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      names: ['Anton', 'Vika', 'Nastya'],
      fullnames: [
        { first: 'Anton', last: 'Makarkin' },
        { first: 'Vika', last: 'Shipko' },
        { first: 'Nastya', last: 'Zhihareva' }
      ],
      actors: [
        {
          name: 'Christian Bale',
          movies: ['Batman', 'The Prestige']
        },
        {
          name: 'Di Caprio',
          movies: ['Titanic', 'Inception']
        }
      ],
      myInfo: {
        name: 'Anton',
        channel: 'Codevolution',
        course: 'Vue 3'
      },
      baseMultiplier: 5
    }
  },
  methods: {
    add(a, b, c) {
      return a + b + c
    },
    multiply(num) {
      return num * this.baseMultiplier
    }
  }
  /*data() {
    return {
      num: '5wfwfwef',
      display: true,
      showElement: true
    }
  }
  /*data() {
    return {
      greet: 'Hello',
      name: 'Anton Makarkin',
      channel: '<b>Codevolution</b>',
      headingId: 'heading',
      isDisabled: false,
      status: 'success',
      isPromoted: true,
      isSoldout: true,
      highlightColor: 'orange',
      headerSize: 50,
      headerStyleObject: {
        color: 'orange',
        fontSize: '50px',
        padding: '20px'
      },
      baseStyleObject: {
        fontSize: '50px',
        padding: '10px'
      },
      successStyleObject: { // last style object gets priority
        color: 'green',
        backgroundColor: 'lightgreen',
        border: '1px solid green'
      },
      dangerStyleObject: {
        color: 'darkred',
        backgroundColor: 'red',
        border: '1px solid darkred'
      }
    }
  }*/
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

.underline {
  text-decoration: underline;
}

.promoted {
  font-style: italic;
}

.new {
  color: olivedrab;
}

.sold-out {
  color: red;
}
</style>
