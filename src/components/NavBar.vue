<template>
  <div>
    <!-- Navbar start -->
    <div>
      <b-navbar toggleable="md" type="dark" variant="info" fixed="top">
        <b-navbar-toggle target="nav_collapse"></b-navbar-toggle>
        <b-navbar-brand href="#">Handys</b-navbar-brand>
        <b-collapse is-nav id="nav_collapse">
          <!-- Right aligned nav items -->
          <b-navbar-nav class="ml-auto">
            <b-nav-item @click="showLoginModal" href="#">로그인</b-nav-item>
            <b-nav-item @click="showSighUpModal1" href="#">회원가입1</b-nav-item>
            <b-nav-item @click="showSighUpModal2" href="#">회원가입2</b-nav-item>
            <b-nav-item @click="showSighUpModal3" href="#">회원가입3</b-nav-item>
          </b-navbar-nav>
        </b-collapse>
      </b-navbar>
    </div>
    <!-- Navbar end -->

    <!-- Login modal -->
    <b-modal ref="Login" hide-header hide-footer>
      <div style="position:absolute; top:1em; right:1em;">
        <button type="button" class="close" @click="hideLoginModal"><span aria-hidden="true">&times;</span></button>
      </div>
      <b-form style="padding:30px;">
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

        <input type="checkbox">
        <a class="login-footer" @mouseover="showImageLoginStatus" @mouseleave="hideImageLoginStatus">
          로그인 상태 유지
        </a>
        <div class="float-right">
          <button class="login-footer">아이디/비밀번호 찾기</button>
          <button class="login-footer" @click="showSighUpModal1">회원가입</button>
        </div>
        <!-- 로그인 버튼 -->
        <div class="float-right">
          <b-btn class="btnModal" type="submit" data-dismiss="modal" @click="hideLoginModal">
            <img src="/static/assets/signImage/login/btnLogin.png">
          </b-btn>
        </div>
        <!-- 로그인 상태 유지 tooltip 이미지-->
        <img id="imgLoginStatus" style="visibility:hidden; position:relative;" src="/static/assets/signImage/login/loginStatus.png" alt="Login status image">
      </b-form>
    </b-modal>

    <!-- signUp1 Modal -->
    <b-modal ref="SignUp1" hide-header hide-footer>
      <div style="position:absolute; top:1em; right:1em;">
        <button type="button" class="close" @click="hideSignUpModal1"><span aria-hidden="true">&times;</span></button>
      </div>
      <modal-signup1></modal-signup1>
      <div class="center">
        <a>
          <img src="static/assets/signImage/membershipAgreement/btnNext.png"
              alt="다음 단계"
              @click="showSighUpModal2">
        </a>
      </div>
    </b-modal>

    <!-- signUp2 Modal -->
    <b-modal ref="SignUp2" hide-header hide-footer>
      <div style="position:absolute; top:1em; right:1em;">
        <button type="button" class="close" @click="hideSignUpModal2"><span aria-hidden="true">&times;</span></button>
      </div>
      <modal-signup2></modal-signup2>
    </b-modal>

    <!-- signUp3 Modal -->
    <b-modal ref="SignUp3" hide-header hide-footer>
      <div style="position:absolute; top:1em; right:1em;">
        <button type="button" class="close" @click="hideSignUpModal2"><span aria-hidden="true">&times;</span></button>
      </div>
      <modal-signup3></modal-signup3>
    </b-modal>

    <!-- emailCode Modal -->
    <div class="modal fade" id="emailCode" tabindex="-1" role="dialog" aria-labelledby="myModalLabel" aria-hidden="true">
      <div class="modal-dialog">
        <div class="modal-content">
          <div style="padding: 8px 16px;">
            <button type="button" class="close" data-dismiss="modal" aria-label="Close"><span aria-hidden="true">&times;</span></button>
          </div>
          <div class="modal-body">
            <h3>인증번호 입력</h3>

            <hr class="col-md-11" style="height:0.5dp; background: #ccc;">

            인증번호가 도착하지 않았을 경우, 스팸함이나 차단 설정을 확인해주세요.<br/>
            확인 후에도 인증번호가 도착하지 않았을 경우, '재발송'을 눌러주세요.
            <h4>회원가입 시 입력하신 <b>euge****@gmail.com</b> (으)로 인증 코드를 발송하였습니다.</h4>
            <h4>이메일로 받은 인증 번호를 입력해 주세요</h4>
            <form class="form-horizontal" action=" " method="post">
              <div class="form-group">
                <div class="col-sm-9">
                  <input type="number" class="form-control" name="emailCode" placeholder="인증번호를 입력해 주세요">
                  <span style="color:red">인증번호가 일치하지 않습니다.</span>
                </div>
                <div class="form-group">
                  <div class="col-sm-offset-8 col-sm-9">
                    <button class="btn btn-primary" data-dismiss="modal"> 재발송 > </button>
                    <button type="submit" class="btn btn-primary" data-dismiss="modal"> 확인 > </button>
                  </div>
                </div>
              </div>
            </form>
          </div>
        </div>
      </div>
    </div>

    <!-- phoneCode Modal -->
    <div class="modal fade" id="phoneCode" tabindex="-1" role="dialog" aria-labelledby="myModalLabel" aria-hidden="true">
      <div class="modal-dialog">
        <div class="modal-content">
          <div style="padding: 8px 16px;">
            <button type="button" class="close" data-dismiss="modal" aria-label="Close"><span aria-hidden="true">&times;</span></button>
          </div>
          <div class="modal-body">
            <h3>인증번호 입력</h3>

            <hr class="col-md-11" style="height:0.5dp; background: #ccc;">

            인증번호가 도착하지 않았을 경우, 스팸함이나 차단 설정을 확인해주세요.<br/>
            확인 후에도 인증번호가 도착하지 않았을 경우, '재발송'을 눌러주세요.
            <h4>회원가입 시 입력하신 <b>0106****789</b> (으)로 인증 코드를 발송하였습니다.</h4>
            <h4>휴대전화로 받은 인증 번호를 입력해 주세요</h4>
            <form class="form-horizontal" action=" " method="post">
              <div class="form-group">
                <div class="col-sm-9">
                  <input type="number" class="form-control" name="phoneCode" placeholder="인증번호를 입력해 주세요">
                  <span style="color:red">숫자만 입력 가능합니다</span>
                </div>
              </div>
              <div class="form-group">
                <div class="col-sm-offset-8 col-sm-9">
                  <button class="btn btn-primary" data-dismiss="modal"> 재발송 > </button>
                  <button type="submit" class="btn btn-primary" data-dismiss="modal"> 확인 > </button>
                </div>
              </div>
            </form>
          </div>
        </div>
      </div>
    </div>

    <!-- signUp3 Modal -->
    <div class="modal fade" id="signUp3" tabindex="-1" role="dialog" aria-labelledby="myModalLabel" aria-hidden="true">
      <div class="modal-dialog">
        <div class="modal-content">
          <div style="padding: 8px 16px;">
            <button type="button" class="close" data-dismiss="modal" aria-label="Close"><span aria-hidden="true">&times;</span></button>
          </div>
          <div class="modal-body">
            <h3><span style="font-weight:normal">WELCOME!</span> 환영합니다.</h3>
            <h3 style="margin-top:0px"><b>핸디즈 회원가입</b></h3>
            <div class="row">
              <div class="col-md-4">1.이용 약관 동의</div>
              <div class="col-md-4">2. 회원정보 입력</div>
              <div class="col-md-4">3. 회원가입 완료</div>
            </div>

            <hr class="col-md-11" style="height:0.5dp; background: #ccc;">

            <div style="text-align:center; padding:1em"> OOO 호스트님,<br/>회원 가입이 완료되었습니다.<br/>앞으로 핸디즈 서비스 이용이 가능합니다.</div>
            <button class="btn btn-primary col-md-offset-5"> 다음 단계 > </button>
          </div>
        </div>
      </div>
    </div>
    
  </div>
</template>

<script>
import ModalLogin from './ModalLogin.vue'
import ModalSignup1 from './ModalSignup1.vue'
import ModalSignup2 from './ModalSignup2.vue'
import ModalSignup3 from './ModalSignup3.vue'

export default {
  components: { ModalLogin, ModalSignup1, ModalSignup2, ModalSignup3 },
  methods: {
    showLoginModal () {
      this.$refs.Login.show()
    },
    showSighUpModal1 () {
      this.$refs.SignUp1.show()
    },
    showSighUpModal2 () {
      this.$refs.SignUp2.show()
    },
    showSighUpModal3 () {
      this.$refs.SignUp3.show()
    },
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

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
/* Login Modal START */
.btnModal {
  background: none;
  border: none;
  padding: 0;
  position: absolute;
  bottom: 10%;
  right: 10%;
}

.login-footer {
  color: #464646;
  font-size: 12px;
  border:none;
}
/* Login Modal END */

</style>
