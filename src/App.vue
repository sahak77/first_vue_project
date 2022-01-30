<template>
  <Header />
  <div> Counter: {{ counter }}</div>
  <span v-bind:title="msg">hover</span>
  <button @click="click">click</button>
  <!--  -->
  <p>{{ inputMsg }}</p>
  <input v-model="inputMsg" />
  <!--  -->
  <div>
    <div v-bind:key="i.id" v-for="i in data">
      {{ i }}
      <span v-if="i.name">aaaaa</span>
      <span v-else-if="i.nick">{{ i.nick }}</span>
      <span v-else>bbbbb</span>
    </div>
  </div>
</template>

<script>
import Header from "./layouts/Header/Header.vue";

export default {
  name: "App",
  components: {
    Header,
  },
  
  
  methods: {
    click () {
      this.counter++
    }
  },

  data () {
  return {
    counter: 0,
    publicPath: 'hello',
    inputMsg: 'hello',
    data : [
      {id: 1, text: 'text1', name: true},
      {id: 2, text: 'text2', name: false},
      {id: 3, text: 'text3', name: true},
      {id: 4, text: 'text4', name: false, nick: 'kampot'},
      ]
  }
},

  renderTriggered({ key, target, type }) {
    console.log({ key, target, type })
  },
  renderTracked({ key, target, type }) {
    console.log({ key, target, type })
  },
  updated () {
    this.$nextTick(function () {
          return 'a'
    // Code that will run only after the
    // entire view has been re-rendered
  })
  },
beforeCreate () {
  console.log(1)
},
created () {
  console.log(2)
},
mounted () {
  console.log(3)
    //   setInterval(() => {
    //   this.counter++
    // }, 1000)
},
};
</script>

<style>
</style>
