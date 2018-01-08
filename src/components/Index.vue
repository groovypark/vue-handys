<template>
  <div>
    <nav-bar></nav-bar>
    <div class="hello">
      <h1>{{ msg }}</h1>
      <!-- Main UI -->
      <div>
        <b-button @click="showModal">
          Open Modal
        </b-button>
        <b-modal ref="myModalRef" hide-footer title="Using Component Methods">
          <div class="d-block text-center">
            <h3>Hello From My Modal!</h3>
          </div>
          <b-btn class="mt-3" variant="outline-danger" block @click="hideModal">Close Me</b-btn>
        </b-modal>
      </div>
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
  methods: {
    showModal () {
      this.$refs.myModalRef.show()
    },
    hideModal () {
      this.$refs.myModalRef.hide()
    }
  },
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
