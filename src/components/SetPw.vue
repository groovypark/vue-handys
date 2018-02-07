<template>
  <div id="set-pw">
    <img class="title" src="static/assets/signImage/setPw/title.png" alt="새로운 비밀번호 설정">
    <hr>
    <img class="text"
         src="static/assets/signImage/setPw/text.png" 
         alt="새로운 비밀번호를 입력해 주세요. 문자와숫자를조합한8자이상이어야합니다.">

    <input class="input" type="text" id="password" placeholder="비밀번호 입력.">
    <input class="input" type="text" id="password" placeholder="비밀번호 확인.">
  </div>
</template>
<script>
export default {
}
</script>
<style scoped>
.title {
  padding-bottom: 23px;
}
hr {
  width:531px;
  height:1px;
  background: #ccc;
}
.text {
  margin: 13px 0 27px 0;
}
.input {
/* @override */
  width: 100%;
  margin-bottom: 18px;
}
</style>
