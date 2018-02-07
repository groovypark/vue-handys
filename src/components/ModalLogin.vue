<template>
  <div id="modal-login">
    <b-form>
      <b-form-group>
        <label for="inputId">
          <img src="/static/assets/signImage/login/id.png">
        </label>
        <input type="email" id="inputId" placeholder="이메일 주소" class="login-input">
      </b-form-group>
      <b-form-group>
        <label for="inputPassword">
          <img src="/static/assets/signImage/login/password.png">
        </label>
        <input type="password" id="inputPassword" placeholder="비밀 번호" class="login-input">
      </b-form-group>

      <input type="checkbox">
      <a class="login-footer" @mouseover="showImageLoginStatus" @mouseleave="hideImageLoginStatus">
        로그인 상태 유지
      </a>
      <div style="float:right">
        <a style="color: #464646; font-size:12px;">아이디/비밀번호 찾기</a>
        <a style="color: #464646; font-size:12px;"> 회원가입</a>
      </div>
      <!-- 로그인 버튼 -->
      <div style="float:right;">
        <b-btn class="btnModal" type="submit" data-dismiss="modal" @click="hideLoginModal" style="position:absolute; left:60%; bottom:10%">
          <img src="/static/assets/signImage/login/btnLogin.png">
        </b-btn>
      </div>
      <!-- 로그인 상태 유지 tooltip 이미지-->
      <img id="imgLoginStatus" style="visibility:hidden; position:relative;" src="/static/assets/signImage/login/loginStatus.png" alt="Login status image">
    </b-form>
  </div>
</template>

<script>
export default {
  name: 'ModalLogin',
  methods: {
    hideLoginModal () {
      this.$refs.Login.hide()
    },
    // 로그인 상태 유지 tooltip
    showImageLoginStatus () {
      document.getElementById('imgLoginStatus').style.visibility = 'visible'
    },
    hideImageLoginStatus () {
      document.getElementById('imgLoginStatus').style.visibility = 'hidden'
    }
  }
}
</script>

<style scoped>
.btnModal {
  background: none;
  border: none;
  padding: 0;
}

.login-input {
  width: 418px;
  height: 23px;
  float: right;
  padding: 6px 11px;
  box-sizing: border-box;
  border: none;
  background-color: #d5d5d5;
  color: #464646;
  font-size: 10px;
}
.login-footer {
  color: #464646;
  font-size: 12px;
}
</style>
