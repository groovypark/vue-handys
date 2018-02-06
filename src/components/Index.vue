<template>
  <div>
    <nav-bar></nav-bar>
    <div class="hello">
      <h1>{{ msg }}</h1>
      
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
      msg: '핸디즈입니다'
    }
  }
}
</script>

<style>
@media (min-width: 576px) {
  div.modal-dialog {
      max-width: 598px;
      margin: 30px auto;
  }
}
.modal-dialog {
  width: 598px;
}
.modal-body {
  padding: 36px 34px 25px 34px;
  text-align: left;
}
.font-notosans {
  font-family: 'Noto Sans KR', sans-serif;
}
.float-right {
  float: right;
}
.center {
  text-align: center;
}
:root {
    --gray: #f3f3f3;
}
.input {
  width: 420px;
  height: 23px;
  float: right;
  padding: 6px 11px;
  box-sizing: border-box;
  border: none;
  background-color: var(--gray);
  color: #464646;
  font-size: 9px;
}
</style>
