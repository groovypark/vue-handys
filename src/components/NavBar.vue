<template>
  <div id="nav-bar">
    <!-- Navbar start -->
    <div>
      <b-navbar toggleable="md" type="dark" variant="info" fixed="top">
        <b-navbar-toggle target="nav_collapse"></b-navbar-toggle>
        <b-navbar-brand href="#">Handys</b-navbar-brand>
        <b-collapse is-nav id="nav_collapse">
          <!-- Right aligned nav items -->
          <b-navbar-nav class="ml-auto">
            <b-nav-item @click="showLoginModal">로그인</b-nav-item>
            <b-nav-item @click="showSignUpModal1">회원가입1</b-nav-item>
            <b-nav-item @click="showSignUpModal2">회원가입2</b-nav-item>
            <b-nav-item @click="showSignUpModal3">회원가입3</b-nav-item>
            <b-nav-item @click="showFindIdPw">찾기</b-nav-item>
            <b-nav-item @click="showPhone">핸드폰</b-nav-item>
            <b-nav-item @click="showEmail">이메일</b-nav-item>
            <b-nav-item @click="showCheckId">아이디확인</b-nav-item>
            <b-nav-item @click="showSetPw">비밀번호</b-nav-item>
          </b-navbar-nav>
        </b-collapse>
      </b-navbar>
    </div>
    <!-- Navbar end -->

    <!-- Login modal -->
    <b-modal ref="Login" hide-header hide-footer>
      <div class="btn-close">
        <button type="button" class="close" @click="hideLoginModal"><span aria-hidden="true">&times;</span></button>
      </div>
      <b-form>
        <b-form-group>
          <label for="inputId">
            <img src="/static/assets/signImage/login/id.png">
          </label>
          <input type="email" id="inputId" placeholder="이메일 주소" class="input">
        </b-form-group>
        <b-form-group>
          <label for="inputPassword">
            <img src="/static/assets/signImage/login/password.png">
          </label>
          <input type="password" id="inputPassword" placeholder="비밀 번호" class="input">
        </b-form-group>

        <div class="login-footer">
          <input class="cursor" type="checkbox">
          <a @mouseover="showImageLoginStatus" @mouseleave="hideImageLoginStatus">
            로그인 상태 유지
          </a>
          <span class="float-right">
            <a class="cursor" @click="showFindIdPw">아이디/비밀번호 찾기 &nbsp</a>
            <a class="cursor" @click="showSignUpModal1">회원가입</a>
          </span>
        </div>
        <!-- 로그인 버튼 -->
        <div class="float-right">
          <a class="btnModal cursor" href="/" @click="hideLoginModal">
            <img src="/static/assets/signImage/login/btnLogin.png">
          </a>
        </div>
        <!-- 로그인 상태 유지 tooltip 이미지-->
        <img id="imgLoginStatus" class="img-login-status" src="/static/assets/signImage/login/loginStatus.png" alt="Login status image">
      </b-form>
    </b-modal>

    <!-- signUp1 Modal -->
    <b-modal ref="SignUp1" hide-header hide-footer>
      <div class="btn-close">
        <button type="button" class="close" @click="hideSignUpModal1"><span aria-hidden="true">&times;</span></button>
      </div>
      <modal-signup1></modal-signup1>
      <div class="center">
        <a>
          <img class="cursor" src="static/assets/signImage/signup1/btnNext.png" alt="다음 단계" @click="showSignUpModal2">
        </a>
      </div>
    </b-modal>

    <!-- signUp2 Modal -->
    <b-modal ref="SignUp2" hide-header hide-footer>
      <div class="btn-close">
        <button type="button" class="close" @click="hideSignUpModal2"><span aria-hidden="true">&times;</span></button>
      </div>
      <modal-signup2></modal-signup2>
      <!-- 버튼 -->
      <a class="btnBefore cursor" @click="showSignUpModal1">
        <img src="static/assets/signImage/signup2/btnBefore.png"
            alt="이전 단계">
      </a>
      <a class="btnNext cursor" @click="showSignUpModal3">
        <img src="static/assets/signImage/signup2/btnNext.png"
            alt="다음 단계">
      </a>
    </b-modal>

    <!-- signUp3 Modal -->
    <b-modal ref="SignUp3" hide-header hide-footer>
      <div class="btn-close">
        <button type="button" class="close" @click="hideSignUpModal3"><span aria-hidden="true">&times;</span></button>
      </div>
      <modal-signup3></modal-signup3>
    </b-modal>

    <!-- FindIdPw Modal -->
    <b-modal ref="FindIdPw" hide-header hide-footer>
      <div class="btn-close">
        <button type="button" class="close" @click="hideFindIdPw"><span aria-hidden="true">&times;</span></button>
      </div>
      <find-id></find-id>

      <img class="btnConfirm cursor" @click="showCheckId" src="static/assets/signImage/btnConfirm.png" alt="확인">

      <find-pw></find-pw>
      <div class="btn cursor">
        <img @click="showEmail" src="static/assets/signImage/findIdPw/btnEmail.png" alt="이메일 인증">
        <img @click="showPhone" src="static/assets/signImage/findIdPw/btnPhone.png" alt="휴대전화 인증">
      </div>
    </b-modal>

    <!-- Phone Modal -->
    <b-modal ref="Phone" hide-header hide-footer>
      <div class="btn-close">
        <button type="button" class="close" @click="hidePhone"><span aria-hidden="true">&times;</span></button>
      </div>
      <phone></phone>
      <!-- 확인 버튼 -->
      <img @click="showSetPw" class="confirm cursor" src="static/assets/signImage/btnConfirm.png" alt="확인">
    </b-modal>

    <!-- Email Modal -->
    <b-modal ref="Email" hide-header hide-footer>
      <div class="btn-close">
        <button type="button" class="close" @click="hideEmail"><span aria-hidden="true">&times;</span></button>
      </div>
      <email></email>
      <!-- 버튼 -->
      <div class="btn-email cursor">
        <img @click="AlertResend" src="static/assets/signImage/email/btnResend.png" alt="재발송">&nbsp &nbsp
        <img @click="showSetPw" src="static/assets/signImage/btnConfirm.png" alt="확인">
      </div>
    </b-modal>

    <!-- CheckId Modal -->
    <b-modal ref="CheckId" hide-header hide-footer>
      <div class="btn-close">
        <button type="button" class="close" @click="hideCheckId"><span aria-hidden="true">&times;</span></button>
      </div>
      <check-id></check-id>
    </b-modal>

    <!-- SetPw Modal -->
    <b-modal ref="SetPw" hide-header hide-footer>
      <div class="btn-close">
        <button type="button" class="close" @click="hideSetPw"><span aria-hidden="true">&times;</span></button>
      </div>
      <set-pw></set-pw>
      <!-- 확인 버튼 -->
      <a href="/" @click="AlertSetPw"><img class="confirm cursor" src="static/assets/signImage/btnConfirm.png" alt="확인"></a>
    </b-modal>
    
  </div>
</template>

<script>
import ModalLogin from './ModalLogin.vue'
import ModalSignup1 from './ModalSignup1.vue'
import ModalSignup2 from './ModalSignup2.vue'
import ModalSignup3 from './ModalSignup3.vue'
import FindId from './FindId.vue'
import FindPw from './FindPw.vue'
import Phone from './Phone.vue'
import Email from './Email.vue'
import CheckId from './CheckId.vue'
import SetPw from './SetPw.vue'

export default {
  components: { ModalLogin, ModalSignup1, ModalSignup2, ModalSignup3, FindId, FindPw, Phone, Email, CheckId, SetPw },
  methods: {
    // show modal
    showLoginModal () {
      this.$refs.Login.show()
    },
    showSignUpModal1 () {
      this.$refs.SignUp1.show()
    },
    showSignUpModal2 () {
      this.$refs.SignUp2.show()
    },
    showSignUpModal3 () {
      this.$refs.SignUp3.show()
    },
    showFindIdPw () {
      this.$refs.FindIdPw.show()
    },
    showPhone () {
      this.$refs.Phone.show()
    },
    showEmail () {
      this.$refs.Email.show()
    },
    showCheckId () {
      this.$refs.CheckId.show()
    },
    showSetPw () {
      this.$refs.SetPw.show()
    },
    // hide modal
    hideLoginModal () {
      this.$refs.Login.hide()
    },
    hideSignUpModal1 () {
      this.$refs.SignUp1.hide()
    },
    hideSignUpModal2 () {
      this.$refs.SignUp2.hide()
    },
    hideSignUpModal3 () {
      this.$refs.SignUp3.hide()
    },
    hideFindIdPw () {
      this.$refs.FindIdPw.hide()
    },
    hidePhone () {
      this.$refs.Phone.hide()
    },
    hideEmail () {
      this.$refs.Email.hide()
    },
    hideCheckId () {
      this.$refs.CheckId.hide()
    },
    hideSetPw () {
      this.$refs.SetPw.hide()
    },
    // 로그인 상태 유지 tooltip
    showImageLoginStatus () {
      document.getElementById('imgLoginStatus').style.visibility = 'visible'
    },
    hideImageLoginStatus () {
      document.getElementById('imgLoginStatus').style.visibility = 'hidden'
    },
    // alert
    AlertSetPw () {
      alert('비밀번호 설정 완료')
    },
    AlertResend () {
      alert('재발송 되었습니다.')
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.btn-close {
  position:absolute;
  top:1em;
  right:1em;
}
/* Login Modal */
.btnModal {
  background: none;
  border: none;
  padding: 0;
  position: absolute;
  bottom: 10%;
  right: 5%;
}
.login-footer {
  color: #464646;
  font-size: 12px;
  border:none;
  margin-left: 110px;
}
.img-login-status {
  visibility: hidden; 
  position: relative;
  margin-left: 110px;
}

/* SignUp2 Modal */
.btnBefore {
  margin-left:103px;
}
.btnNext {
  float:right;
  margin-right:103px;
}

/* FindIdPw Modal */
div.btn {
  float: right;
  padding: 0;
  margin: 44px 0 27px 0;
}
.btnConfirm {
  float: right;
  margin: 13px 0 41px 0;
}

 /* Phone Modal */
.confirm {
  float: right;
  margin-bottom: 10px;
}

/* Email Modal */
.btn-email {
  float: right;
  padding: 0;
}
</style>
