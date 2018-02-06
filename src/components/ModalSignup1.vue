<template>
  <div class="ModalSignup1">
    <img src="static/assets/signImage/signup1/welcome.png"
         alt="WELCOME! 환영합니다. 핸디즈 회원가입">
    <img class="agreement-header"
         src="static/assets/signImage/signup1/order1.png"
         alt="1.이용 약관 동의">
    <hr>
    <img src="static/assets/signImage/signup1/agreementTitle.png"
         alt="핸디즈 서비스 이용약관 및 개인정보 활용 동의 내용을  확인하였으며, 아래 내용에 동의합니다.">
    <a class="btn-all-agree">
      <img src="static/assets/signImage/signup1/allAgreeOff.png"
           alt="모두 동의">
    </a>
    <hr>
    <div class="font-notosans font-agreement">
      이용 약관 동의 (필수)
      <a class="float-right">
        <img src="static/assets/signImage/signup1/agreeOff.png"
             alt="동의 하기">
      </a>
    </div>
    <div class="div-scroll">
      이용약관 동의 (필수)이용약관 동의 (필수)이용약관 동의 (필수)이용약관 동의 (필수)<br/>
      이용약관 동의 (필수)이용약관 동의 (필수)이용약관 동의 (필수)<br/>
      이용약관 동의 (필수)이용약관 동의 (필수)이용약관 동의 (필수)<br/>
      이용약관 동의 (필수)이용약관 동의 (필수)<br/>
    </div>

    <div class="font-notosans font-agreement">
      개인정보 취급 방침 동의(필수)
      <a class="float-right">
        <img src="static/assets/signImage/signup1/agreeOff.png"
             alt="동의 하기">
      </a>
    </div>
    <div class="div-scroll">
      이용약관 동의 (필수)이용약관 동의 (필수)이용약관 동의 (필수)이용약관 동의 (필수)<br/>
      이용약관 동의 (필수)이용약관 동의 (필수)이용약관 동의 (필수)<br/>
      이용약관 동의 (필수)이용약관 동의 (필수)이용약관 동의 (필수)<br/>
      이용약관 동의 (필수)이용약관 동의 (필수)<br/>
    </div>
  </div>
</template>
<script>
export default {
  name: 'ModalSignup1'
}
</script>
<style scoped>
hr {
  width:531px;
  height:1px;
  background: #ccc;
}

.agreement-header {
  margin-top:30px;
}

.btn-all-agree {
  float:right;
  margin-top:5px;
}

.font-agreement {
  font-size: 16px;
  letter-spacing: -0.8px;
  text-align: left;
  color: #000000;
}

.div-scroll {
  overflow:scroll;
  margin: 11px 0 33px 0;
  width:531px;
  height:86px;
  background-color:#f3f3f3;
  font-size: 10px;
  padding: 15px;
}
</style>
