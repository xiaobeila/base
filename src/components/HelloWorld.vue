<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h2>Essential Links</h2>
    <ul>
      <li>
        <a href="https://vuejs.org" target="_blank">
          Core Docs
        </a>
      </li>
      <li>
        <a href="https://forum.vuejs.org" target="_blank">
          Forum
        </a>
      </li>
      <li>
        <a href="https://chat.vuejs.org" target="_blank">
          Community Chat
        </a>
      </li>
      <li>
        <a href="https://twitter.com/vuejs" target="_blank">
          Twitter
        </a>
      </li>
      <br>
      <li>
        <a href="http://vuejs-templates.github.io/webpack/" target="_blank">
          Docs for This Template
        </a>
      </li>
    </ul>
    <h2>Ecosystem</h2>
    <ul>
      <li>
        <a href="http://router.vuejs.org/" target="_blank">
          vue-router
        </a>
      </li>
      <li>
        <a href="http://vuex.vuejs.org/" target="_blank">
          vuex
        </a>
      </li>
      <li>
        <a href="http://vue-loader.vuejs.org/" target="_blank">
          vue-loader
        </a>
      </li>
      <li>
        <a href="https://github.com/vuejs/awesome-vue" target="_blank">
          awesome-vue
        </a>
      </li>
    </ul>
    <div class="components-container" style='height:100vh'>
      <div class='chart-container'>
        <keyboard-chart v-if="chartData && chartKeyData" height='100%' width='100%' :chartData="chartData" :chartKeyData="chartKeyData" :name="charName"></keyboard-chart>
      </div>
    </div>
  </div>
</template>

<script>
import keyboardChart from 'base/Charts/keyboard'

export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      chartData: null,
      chartKeyData: null,
      charName: '小林'
    }
  },
  components: { keyboardChart },
  mounted () {
    let xAxisData = []
    let data = []
    for (let i = 0; i < 30; i++) {
      xAxisData.push(i + '号')
      data.push(Math.round(Math.random() * 2 + 3))
    }
    this.chartData = xAxisData
    this.chartKeyData = data
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1,
h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.chart-container {
  position: relative;
  width: 100%;
  height: 90%;
}
</style>
