<template>
  <div>
    <app-nav></app-nav>
    <nav-bar></nav-bar>
    <div class="hello">
      <h1>{{ msg }}</h1>
      <img v-bind:src="img"/>
      <img src="https://files.slack.com/files-tmb/T8N3E1MA9-F8NQQLTP0-87cb498054/_____________________________________1024.jpg">
      <img src="https://files.slack.com/files-tmb/T8N3E1MA9-F8NQQLTP0-87cb498054/_____________________________________1024.jpg">
      <img src="https://files.slack.com/files-tmb/T8N3E1MA9-F8NQQLTP0-87cb498054/_____________________________________1024.jpg">
    </div>
  </div>
</template>

<script>
import NavBar from './NavBar.vue'
export default {
  name: 'Index',
  components: { NavBar },
  data () {
    return {
      msg: '핸디즈입니다',
      img: './src/assets/btn_login.png'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
  font-family: 'Noto Sans KR', sans-serif;
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
</style>
