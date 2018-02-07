<template>
  <div id="check-id">
    <img class="title" src="static/assets/signImage/checkId/title.png" alt="아이디 확인">
    <hr>
    <img class="text"
         src="static/assets/signImage/checkId/text.png" 
         alt="인증번호가 도착하지 않았을 경우, 스팸함이나 차단 설정을 확인해주세요. 확인 후에도 인증번호가 도착하지 않을 경우 '재발송'을 눌러주세요.">

    <div>회원님의 아이디는 &nbsp;<span><b>euge******@gm**l.com</b></span>&nbsp; 입니다.</div>
    
    <!-- 확인 버튼 -->
    <a href="/"><img class="confirm" src="static/assets/signImage/btnConfirm.png" alt="확인"></a>
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
  margin: 15px 0 17px 0;
}
.confirm {
  margin-top: 25px;
  float: right;
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
</style>
