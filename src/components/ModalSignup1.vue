<template>
  <div id="modal-signup1">
    <img src="static/assets/signImage/signup1/welcome.png"
         alt="WELCOME! 환영합니다. 핸디즈 회원가입">
    <img class="agreement-header"
         src="static/assets/signImage/signup1/order1.png"
         alt="1.이용 약관 동의">
    <hr>
    <img src="static/assets/signImage/signup1/agreementTitle.png"
         alt="핸디즈 서비스 이용약관 및 개인정보 활용 동의 내용을  확인하였으며, 아래 내용에 동의합니다.">
    <a class="btn-all-agree" @click='toggleAllAgree(), checkAllAgree()'>
      <img :src="allAgree ? allAgreeOn : allAgreeOff"
              alt="모두 동의">
    </a>
    <hr>
    <div class="font-notosans font-agreement">
      이용 약관 동의 (필수)
      <a class="float-right" @click='agree1 = !agree1, checkAllAgree()'>
        <img :src="agree1 ? agreeOn : agreeOff"
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
      <a class="float-right" @click='agree2 = !agree2, checkAllAgree()'>
        <img :src="agree2 ? agreeOn : agreeOff"
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
  name: 'ModalSignup1',
  data: function () {
    return {
      allAgree: false,
      agree1: false,
      agree2: false,
      allAgreeOn: 'static/assets/signImage/signup1/allAgreeOn.png',
      allAgreeOff: 'static/assets/signImage/signup1/allAgreeOff.png',
      agreeOn: 'static/assets/signImage/signup1/agreeOn.png',
      agreeOff: 'static/assets/signImage/signup1/agreeOff.png'
    }
  },
  methods: {
    // 모두동의 버튼 조건 체크
    checkAllAgree () {
      if (this.agree1 === true && this.agree2 === true) {
        this.allAgree = true
      } else {
        this.allAgree = false
      }
    },
    toggleAllAgree () {
      if (this.allAgree === true) {
        this.allAgree = false
        this.agree1 = false
        this.agree2 = false
      } else {
        this.allAgree = true
        this.agree1 = true
        this.agree2 = true
      }
    }
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
