<template>
  <div id="email">
    <img class="title" src="static/assets/signImage/phone/title.png" alt="인증번호 입력">
    <hr>
    <img class="text"
         src="static/assets/signImage/phone/text.png" 
         alt="인증번호가 도착하지 않았을 경우, 스팸함이나 차단 설정을 확인해주세요. 확인 후에도 인증번호가 도착하지 않을 경우, '재발송'을 눌러주세요.">

    <div>회원가입 시 입력하신 <span><b>euge****@gmail.com</b></span> (으)로 인증 코드를 발송하였습니다.</div>
    
    <img class="input-title" src="static/assets/signImage/email/input-title.png" alt="이메일로 받은 인증 번호를 입력해 주세요.">
    <input class="input" type="tel" id="emailCode" placeholder="인증번호를 입력해 주세요.">
    <div class="err-text font-notosans">인증번호가 일치하지 않습니다.</div>
    <!-- 버튼 -->
    <div class="btn">
      <img src="static/assets/signImage/email/btnResend.png" alt="재발송">&nbsp &nbsp
      <img src="static/assets/signImage/btnConfirm.png" alt="확인">
    </div>
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
  margin: 15px 0 27px 0;
}
.input-title {
  margin: 38px 0 15px 0;
}
.input {
/* @override */
  width: 100%;
}
.err-text {
  font-size: 10px;
	line-height: 3.5;
	letter-spacing: -0.5px;
	text-align: left;
	color: #e60012;
}
.btn {
  float: right;
  padding: 0;
}
</style>
