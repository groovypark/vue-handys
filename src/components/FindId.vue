<template>
  <div class="find-id">
    <img src="static/assets/signImage/findIdPw/title.png" alt="로그인이 안 되나요? 아이디 및 비밀번호 찾기">
    <hr>
    <img src="static/assets/signImage/findIdPw/findId.png" alt="아이디 찾기"><br/>
    <img class="explanation" src="static/assets/signImage/findIdPw/findIdText.png" alt="회원정보를 확인하여 아이디를 찾아드립니다."><br/>
    
    <div>
      <img src="static/assets/signImage/findIdPw/name.png" alt="이름">
      <input class="input" type="text" name="name" placeholder=" 이름을 입력하세요.">
    </div>
    <div class="input-margin">
      <img src="static/assets/signImage/findIdPw/phone.png" alt="전화번호">
      <input class="input" type="text" name="name" placeholder=" 휴대전화 번호를 입력하세요.">
    </div>
    <div class="err-text">회원 가입이 안된 회원입니다.</div>
  </div>
</template>
<script>
export default {
  name: 'FindId'
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
