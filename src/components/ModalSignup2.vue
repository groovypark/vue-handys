<template>
  <div id="modal-signup2" class="font-notosans" style="font-size:15px;">
    <img src="static/assets/signImage/signup1/welcome.png"
         alt="WELCOME! 환영합니다. 핸디즈 회원가입">
    <img class="agreement-header"
         src="static/assets/signImage/signup2/order2.png"
         alt="2.회원정보 입력">
    <hr>
    <b-form>
      <!---------- 이름 ---------->
      <b-form-group>
        <label for="name">
          <img src="static/assets/signImage/signup2/name.png"
               alt="이름">
        </label>
          <input class="input" type="text" name="name">
          <div class="err-text font-notosans">필수 항목입니다.</div>
      </b-form-group>
      <!---------- 전화번호 ---------->
      <b-form-group>
        <label for="phoneNumber">
          <img src="static/assets/signImage/signup2/phone.png"
               alt="전화번호">
        </label>
          <input class="input" type="tel" name="phoneNumber" placeholder="휴대전화 번호를 입력해 주세요.">
          <div class="err-text font-notosans">필수 항목입니다.</div>
      </b-form-group>
      <!---------- 전화번호 인증 ---------->
      <b-form-group>
        <label for="phoneNumberCheck">
          <img src="static/assets/signImage/signup2/phoneNum.png"
            alt="전화번호 인증">
        </label>
        <span style="float:right;">
          <a class="cursor" style="margin-right:6px;">
            <img v-bind:src="btnUrl"
              alt="인증번호 받기" @click="changeBtn()">
          </a>
          <a class="cursor" ref="resend" v-bind:style="visibility">
            <img src="static/assets/signImage/signup2/resendOff.png"
              alt="재발송">
          </a>
        </span>
        <input class="input" style="width:191px; margin-right:8px;" type="text" name="phoneNumberCheck" placeholder="문자로 받은 인증번호 6자리 입력해 주세요.">
        <div class="err-text font-notosans">인증코드를 발송하였습니다.</div>
      </b-form-group>
      <!---------- 아이디 ---------->
      <b-form-group>
        <label for="id">
          <img src="static/assets/signImage/signup2/id.png"
            alt="아이디">
        </label>
        <input class="input" type="email" name="id" placeholder="E-mail 주소를 입력해 주세요.">
        <div class="err-text font-notosans">정확한 E-mail 주소를 입력해 주세요.</div>
      </b-form-group>
      <!---------- 비밀번호 ---------->
      <b-form-group>
        <label for="password">
          <img src="static/assets/signImage/signup2/password.png"
            alt="비밀번호">
        </label>
        <input class="input" type="text" name="password" placeholder="">
        <div class="err-text font-notosans">문자와 숫자 조합으로 8자 이상 입력해 주세요.</div>
      </b-form-group>
      <!---------- 비밀번호 확인 ---------->
      <b-form-group>
        <label for="passwordCheck">
          <img src="static/assets/signImage/signup2/checkPw.png"
            alt="비밀번호 확인">
        </label>
        <input class="input" type="text" name="passwordCheck" placeholder="">
        <div class="err-text font-notosans">비밀번호가 일치하지 않습니다.</div>
      </b-form-group>
      <!---------- 성별  ---------->
      <b-form-group>
        <label for="gender">
          <img src="static/assets/signImage/signup2/gender.png"
            alt="성별">
        </label>
        <span v-for="gender in genders" :key="gender.id">
          <input class="radio-gender cursor" name="gender" type="radio" v-bind:value="gender.value"> {{ gender.text }}
        </span>
      </b-form-group>
      <!---------- 연령대 ---------->
      <b-form-group>
        <label for="age" style="float:left;">
          <img src="static/assets/signImage/signup2/age.png"
            alt="연령대">
        </label>
        <table style="margin-left:107px;">
            <tr>
              <td style="width:121px; height:46px; vertical-align:top;" v-for="age in ages1" :key="age.id">
                <input class="cursor" type="radio" name="age" v-bind:value="age.value"> {{ age.text }}
              </td>
            </tr>
            <tr>
              <td v-for="age in ages2" :key="age.id">
                <input class="cursor" type="radio" name="age" v-bind:value="age.value"> {{ age.text }}
              </td>
            </tr>
        </table>
      </b-form-group>
      <!---------- 호스팅 지역 ---------->
      <form style="margin-top: 23px; margin-bottom:30px">
        <label for="local" style="margin-right:32px;">
          <img src="static/assets/signImage/signup2/local.png"
            alt="호스팅 지역">
        </label>
        <span style="margin-right:73px;" v-for="local in locals" :key="local.id">
          <input class="cursor" type="radio" name="local" v-bind:value="local.value"> {{ local.text }}
        </span>
      </form>
    </b-form>
  </div>
</template>
<script>
export default {
  name: 'ModalSignup1',
  data: function () {
    return {
      visibility: 'visibility:hidden;',
      btnUrl: 'static/assets/signImage/signup2/phoneNumOff.png',
      genders: [
        { text: '남성', value: 'male' },
        { text: '여성', value: 'femal' }
      ],
      ages1: [
        { text: '10대 이하', value: 10 },
        { text: '20대', value: 20 },
        { text: '30대', value: 30 }
      ],
      ages2: [
        { text: '40대', value: 40 },
        { text: '50대', value: 50 },
        { text: '60대 이상', value: 60 }
      ],
      locals: [
        { text: '서울', value: 'seoul' },
        { text: '부산', value: 'busan' },
        { text: '제주', value: 'jeju' },
        { text: '그 외', value: 'etc' }
      ]
    }
  },
  methods: {
    changeBtn () {
      this.visibility = 'visibility:visible;'
      this.btnUrl = 'static/assets/signImage/signup2/verifyOff.png'
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

.err-text {
  font-size: 10px;
	line-height: 1.6;
	letter-spacing: -0.5px;
	text-align: left;
	color: #e60012;
  margin-left: 110px;
}
.radio-gender {
  margin-left: 75px;
}
.radio-age {
  float: right;
  margin-right: 65px;
}

label.form-check-label {
  margin-left: 40px;
}
</style>