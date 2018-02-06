<template>
  <div class="ModalSignup2">
    <img src="static/assets/signImage/signup1/welcome.png"
         alt="WELCOME! 환영합니다. 핸디즈 회원가입">
    <img class="agreement-header"
         src="static/assets/signImage/signup2/order2.png"
         alt="2.회원정보 입력">
    <hr>
    <b-form>
      <!-- 이름 -->
      <b-form-group>
        <label for="name">
          <img src="static/assets/signImage/signup2/name.png"
               alt="이름">
        </label>
          <input class="input" type="text" name="name">
          <div class="err-text font-notosans">필수 항목입니다</div>
      </b-form-group>
      <!-- 전화번호 -->
      <b-form-group>
        <label for="phoneNumber">
          <img src="static/assets/signImage/signup2/phone.png"
               alt="전화번호">
        </label>
          <input class="input" type="number" name="phoneNumber" placeholder="휴대전화 번호를 입력해 주세요">
          <div class="err-text font-notosans">필수 항목입니다</div>
      </b-form-group>
      <!-- 전화번호 인증 -->
      <b-form-group>
        <label for="phoneNumberCheck" style="width:115px;">
          <img src="static/assets/signImage/signup2/phoneNum.png"
            alt="전화번호 인증">
        </label>
        <input class="input" type="number" name="phoneNumberCheck" placeholder="문자로 받은 인증번호 6자리 입력해 주세요">
        <a>
          <img src="static/assets/signImage/signup2/phoneNumOff.png"
            alt="인증번호 받기">
        </a>
        <a>
          <img src="static/assets/signImage/signup2/resendOff.png"
            alt="재발송">
        </a>
          <div class="err-text font-notosans">인증코드를 발송하였습니다</div>
      </b-form-group>
      <!-- 아이디 -->
      <b-form-group>
        <label for="id">
          <img src="static/assets/signImage/signup2/id.png"
            alt="아이디">
        </label>
        <input class="input" type="email" name="id" placeholder="E-mail 주소를 입력해 주세요">
        <div class="err-text font-notosans">정확한 E-mail 주소를 입력해 주세요</div>
      </b-form-group>
      <!-- 비밀번호 -->
      <b-form-group>
        <label for="password">
          <img src="static/assets/signImage/signup2/password.png"
            alt="비밀번호">
        </label>
        <input class="input" type="text" name="password" placeholder="">
        <div class="err-text font-notosans">문자와 숫자 조합으로 8자 이상 입력해 주세요</div>
      </b-form-group>
      <!-- 비밀번호 확인 -->
      <b-form-group>
        <label for="passwordCheck">
          <img src="static/assets/signImage/signup2/checkPw.png"
            alt="비밀번호 확인">
        </label>
        <input class="input" type="text" name="passwordCheck" placeholder="">
        <div class="err-text font-notosans">비밀번호가 일치하지 않습니다.</div>
      </b-form-group>
      <!-- 성별 -->
      <b-form-group>
        <label for="gender">
          <img src="static/assets/signImage/signup2/gender.png"
            alt="성별">
        </label>
        <input type="radio" name="gender"> 남성
        <input type="radio" name="gender"> 여성
      </b-form-group>
      <!-- 연령대 -->
      <b-form-group>
        <label for="age">
          <img src="static/assets/signImage/signup2/age.png"
            alt="연령대">
        </label>
        <input type="radio" name="10"> 10대 이하
        <input type="radio" name="20"> 20대
        <input type="radio" name="30"> 30대
        <input type="radio" name="40"> 40대
        <input type="radio" name="50"> 50대
        <input type="radio" name="60"> 60대 이상
      </b-form-group>
      <!-- 호스팅 지역 -->
      <b-form-group>
        <label for="local">
          <img src="static/assets/signImage/signup2/local.png"
            alt="호스팅 지역">
        </label>
        <input type="radio" name="seoul"> 서울
        <input type="radio" name="busan"> 부산
        <input type="radio" name="jeju"> 제주
        <input type="radio" name="etcl"> 그 외
      </b-form-group>
    </b-form>

    <!-- 버튼 -->
    <div class="form-group">
      <a style="margin-left:103px;">
        <img src="static/assets/signImage/signup2/btnBefore.png"
            alt="이전 단계">
      </a>
      <a style="float:right; margin-right:103px;">
        <img src="static/assets/signImage/signup2/btnNext.png"
            alt="다음 단계">
      </a>
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

.err-text {
  font-size: 10px;
	line-height: 1.6;
	letter-spacing: -0.5px;
	text-align: left;
	color: #e60012;
  margin-left: 135px;
}
</style>