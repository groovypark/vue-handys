<template>
  <div class="find-pw">
    <hr class="hr-margin">
    <img src="static/assets/signImage/findIdPw/findPw.png" alt="비밀번호 찾기"><br/>
    <img class="explanation" src="static/assets/signImage/findIdPw/findPwText.png" alt="본인 인증으로 비밀번호를 변경하세요.">
    <div class="input-margin">
      <img src="static/assets/signImage/findIdPw/id.png" alt="ID 입력">
      <input class="input" type="text" name="id" placeholder=" E-mail 주소를입력하세요.">
    </div>
    <div class="err-text">가입되지 않은 메일주소 입니다. </div>
  </div>
</template>
<script>
export default {
  name: 'FindPw'
}
</script>
<style scoped>
.explanation {
  margin: 9px 0 43px 0;
}
.input-margin {
  margin: 9px 0 12px 0;
}
.err-text {
  font-size: 10px;
	line-height: 1.6;
	letter-spacing: -0.5px;
	text-align: left;
	color: #e60012;
  margin-left: 110px;
}
hr {
  width:531px;
  height:1px;
  background: #ccc;
}
.hr-margin {
  margin: 91px 0 37px 0;
}
</style>