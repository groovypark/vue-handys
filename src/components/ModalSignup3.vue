<template>
  <div class="ModalSignup1">
    <img src="static/assets/signImage/signup1/welcome.png"
         alt="WELCOME! 환영합니다. 핸디즈 회원가입">
    <img class="agreement-header"
         src="static/assets/signImage/signup3/order3.png"
         alt="1.이용 약관 동의">
    <hr>
    <div style="text-align:center;">
      OOO 호스트님,<br/>
      회원 가입이 완료되었습니다.<br/>
      앞으로 핸디즈 서비스 이용이 가능합니다.<br/>
      <img src="static/assets/signImage/signup3/clap.png"
           alt="박수">
      <img src="static/assets/signImage/signup3/btnHome.png"
           alt="홈으로">
    </div>
  </div>
</template>
<script>
export default {
  name: 'ModalSignup3',
  methods: {

  }
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
</style>
