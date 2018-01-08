<template>
  <div>
    <!-- Navbar start -->
    <div>
      <b-navbar toggleable="md" type="dark" variant="info" fixed="top">

        <b-navbar-toggle target="nav_collapse"></b-navbar-toggle>

        <b-navbar-brand href="#">NavBar</b-navbar-brand>

        <b-collapse is-nav id="nav_collapse">

          <b-navbar-nav>
            <b-nav-item href="#">Link</b-nav-item>
          </b-navbar-nav>

          <!-- Right aligned nav items -->
          <b-navbar-nav class="ml-auto">
            <b-nav-item v-b-modal.modalLogin href="#">Login</b-nav-item>
            <b-nav-item v-b-modal.modalLink href="#">Link</b-nav-item>
            <b-nav-item href="#">Link</b-nav-item>
          </b-navbar-nav>

        </b-collapse>
      </b-navbar>
    </div>
    <!-- Navbar end -->

    <div>
      <b-modal id="modalLink" hide-header hide-footer>
        <div style="padding: 8px 16px;">
          <button type="button" class="close" data-dismiss="modal" aria-label="Close"><span aria-hidden="true">&times;</span></button>
        </div>
        <label for="inputId" class="col-sm-2 control-label"><img src="/static/assets/signImage/login/id.png"></label>
        <a href="#" v-b-tooltip title="Tooltip in a modal!">Link</a>

        <div class="form-group">
                <label for="inputId" class="col-sm-2 control-label"><img src="/static/assets/signImage/login/id.png"></label>
                <div class="col-sm-9">
                  <input type="email" class="form-control" id="inputId" placeholder="이메일 주소">
                </div>
              </div>
              <div class="form-group">
                <label for="inputPassword" class="col-sm-2 control-label">PW</label>
                <div class="col-sm-9">
                  <input type="password" class="form-control" id="inputPassword" placeholder="비밀 번호">
                </div>
              </div>
              <div class="form-group">
                <div class="col-sm-offset-2 col-sm-9">
                  <div class="checkbox">
                    <label>
                      <input type="checkbox">
                      <a data-toggle="tooltip" 
                      data-placement="bottom" 
                      title="체크 후 로그인하시면 로그인 상태가 유지됩니다.
공공장소에서 사용할 경우, 개인정보가 도용될 수 있으니, 개인PC에서만 사용하시기 바랍니다.">
                        로그인 상태 유지
                      </a>
                    </label>
                    <div style="float:right">
                      <a>아이디/비밀번호 찾기</a>
                      <a>회원가입</a>
                    </div>
                  </div>
                </div>
              </div>
              <div class="form-group">
                <div class="col-sm-offset-9 col-sm-9">
                  <button class="btnModal" type="submit" data-dismiss="modal"><img src="/static/assets/signImage/login/btnLogin.png"></button>
                </div>
              </div>
      </b-modal>
    </div>

    <!-- login Modal -->
    <div class="modal fade" id="login" tabindex="-1" role="dialog" aria-labelledby="myModalLabel" aria-hidden="true">
      <div class="vertical-align-top">
        <div class="modal-dialog vertical-align-top">
          <div class="modal-content">
            <div style="padding: 8px 16px;">
              <button type="button" class="close" data-dismiss="modal" aria-label="Close"><span aria-hidden="true">&times;</span></button>
            </div>
            <form class="form-horizontal" action=" " method="post">
              <div class="form-group">
                <label for="inputId" class="col-sm-2 control-label"><img src="/static/assets/signImage/login/id.png"></label>
                <div class="col-sm-9">
                  <input type="email" class="form-control" id="inputId" placeholder="이메일 주소">
                </div>
              </div>
              <div class="form-group">
                <label for="inputPassword" class="col-sm-2 control-label">PW</label>
                <div class="col-sm-9">
                  <input type="password" class="form-control" id="inputPassword" placeholder="비밀 번호">
                </div>
              </div>
              <div class="form-group">
                <div class="col-sm-offset-2 col-sm-9">
                  <div class="checkbox">
                    <label>
                      <input type="checkbox">
                      <a data-toggle="tooltip" 
                      data-placement="bottom" 
                      title="체크 후 로그인하시면 로그인 상태가 유지됩니다.
공공장소에서 사용할 경우, 개인정보가 도용될 수 있으니, 개인PC에서만 사용하시기 바랍니다.">
                        로그인 상태 유지
                      </a>
                    </label>
                    <div style="float:right">
                      <a>아이디/비밀번호 찾기</a>
                      <a>회원가입</a>
                    </div>
                  </div>
                </div>
              </div>
              <div class="form-group">
                <div class="col-sm-offset-9 col-sm-9">
                  <button type="submit" class="btn btn-primary" data-dismiss="modal"> 로그인 > </button>
                </div>
              </div>
            </form>
          </div>
        </div>
      </div>
    </div>

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

    <!-- signUp2 Modal -->
    <div class="modal fade" id="signUp2" tabindex="-1" role="dialog" aria-labelledby="myModalLabel" aria-hidden="true">
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

            <form class="form-horizontal" action=" " method="post">
              <!-- 이름 -->
              <div class="form-group">
                <label for="name" class="col-sm-2 control-label">이름</label>
                <div class="col-sm-9">
                  <input type="text" class="form-control" name="name">
                  <span style="color:red">필수 항목입니다</span>
                </div>
              </div>
              <!-- 전화번호 -->
              <div class="form-group">
                <label for="phoneNumber" class="col-sm-2 control-label">전화번호</label>
                <div class="col-sm-9">
                  <input type="number" class="form-control" name="phoneNumber" placeholder="휴대전화 번호를 입력해 주세요">
                  <span style="color:red">필수 항목입니다</span>
                </div>
              </div>
              <!-- 전화번호인증 -->
              <div class="form-group">
                <label for="phoneNumberCheck" class="col-sm-2 control-label" style="width:115px;">전화번호 인증</label>
                <div class="col-sm-9">
                  <div class="row">
                    <div style="width:20em" class="col-xs-8">
                      <input type="number" class="form-control" name="phoneNumberCheck" placeholder="문자로 받은 인증번호 6자리 입력해 주세요">
                    </div>
                    <div style="width:10em" class="col-xs-offset-7"><button>인증번호 받기 ></button></div>
                  </div>
                  <span style="color:red">인증코드를 발송하였습니다</span>
                </div>
              </div>
              <!-- 아이디 -->
              <div class="form-group">
                <label for="id" class="col-sm-2 control-label">아이디</label>
                <div class="col-sm-9">
                  <input type="email" class="form-control" name="id" placeholder="E-mail 주소를 입력해 주세요">
                  <span style="color:red">정확한 E-mail 주소를 입력해 주세요</span>
                </div>
              </div>
              <!-- 비밀번호 -->
              <div class="form-group">
                <label for="password" class="col-sm-2 control-label">비밀번호</label>
                <div class="col-sm-9">
                  <input type="text" class="form-control" name="password" placeholder="">
                  <span style="color:red">문자와 숫자 조합으로 8자 이상 입력해 주세요</span>
                </div>
              </div>
              <!-- 비밀번호 확인 -->
              <div class="form-group">
                <label for="passwordCheck" class="col-sm-2 control-label">비밀번호 확인</label>
                <div class="col-sm-9">
                  <input type="text" class="form-control" name="passwordCheck" placeholder="">
                  <span style="color:red">비밀번호가 일치하지 않습니다.</span>
                </div>
              </div>
              <!-- 성별 -->
              <div class="form-group">
                <label for="gender" class="col-sm-2 control-label">성별</label>
                <div class="col-sm-9">
                  <input type="radio" name="gender"> 남성
                  <input type="radio" name="gender"> 여성
                </div>
              </div>
              <!-- 성별 -->
              <div class="form-group">
                <label for="gender" class="col-sm-2 control-label">연령대</label>
                <div class="col-sm-9">
                  <input type="radio" name="age"> 10대 이하
                  <input type="radio" name="age"> 20대
                  <input type="radio" name="age"> 30대
                  <input type="radio" name="age"> 40대
                  <input type="radio" name="age"> 50대
                  <input type="radio" name="age"> 60대 이상
                </div>
              </div>
              <!-- 성별 -->
              <div class="form-group">
                <label for="gender" class="col-sm-2 control-label">호스팅 지역</label>
                <div class="col-sm-9">
                  <input type="radio" name="place"> 서울
                  <input type="radio" name="place"> 부산
                  <input type="radio" name="place"> 제주
                  <input type="radio" name="place"> 그 외
                </div>
              </div>

              <!-- 버튼 -->
              <div class="form-group">
                <div class="col-sm-offset-4 col-sm-9">
                  <button class="btn btn-primary" data-dismiss="modal"> 이전 단계 > </button>
                  <button type="submit" class="btn btn-primary" data-dismiss="modal"> 다음 단계 > </button>
                </div>
              </div>
            </form>
          </div>
        </div>
      </div>
    </div>
    
    <!-- signUp Modal -->
    <div class="modal fade" id="signUp" tabindex="-1" role="dialog" aria-labelledby="myModalLabel" aria-hidden="true">
      <div class="modal-dialog">
        <div class="modal-content">
          <div style="padding: 8px 16px;">
            <button type="button" class="close" data-dismiss="modal" aria-label="Close"><span aria-hidden="true">&times;</span></button>
          </div>
          <div class="">
            <img src="static/assets/signImage/membershipAgreement/welcome.png"></img>
            <div class="row">
              <div class="col-md-4">1.이용 약관 동의</div>
              <div class="col-md-4">2. 회원정보 입력</div>
              <div class="col-md-4">3. 회원가입 완료</div>
            </div>

            <hr class="col-md-11" style="height:0.5dp; background: #ccc;">

            <div class="row">
                <div class="col-md-10">
                  핸디즈 서비스 이용약관 및 개인정보 활용 동의 내용을<br/>
                  확인하였으며, 아래 내용에 동의합니다.
                </div>
                <div class="sinUp_right"><button>모두동의 ></button></div>
            </div>

            <hr class="col-md-11" style="height:0.5dp; background: #ccc;">

            <div class="row">
              <div class="col-md-9">이용 약관 동의(필수)</div>
              <div class="sinUp_right"><button>동의하기 ></button></div>
            </div>
            <div class="divSignUp" style="overflow:scroll;">
              이용ㅇㅇㅇㅇㅇㅇㅇㅇㅇㅇㅇ약ㄲㄲㄲㄲㄲㄲㄲㄲㄲㄲ곽ㄴㄴㄴㄴㄴㄴㄴㄴㄴㄴㄴㄴㄴㄴㄴㄴㄴㄴㄴㄴㄴㄴㄴㅇ미ㅜㄹ머ㅜㅇㅁ우림ㅇㅇㅇㅇㅇㅇㅇㅇㅇㅇㅇㅇㅇㅇㅇㅇㅇㅇㅇㅇㅇㅇㅇㅇㅇㅇㅇ
              ㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅋㅋㅋㅋㅋㅋㅋㅋㅋㅋㅋㅋㅋㅋㅋㅋasdffffffffffffffffffffffffffaㅁㄴㅇㄹㅁㄴㅇㄹㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁ
              ㅁㄴㅇㄹㄹㄹㄹㄹㄹㄹㄹㄹㄹㄹㄹㄹㄹㄹㄹㄹㄹㄹㄹㄹㄹㄹㄹㄹㄹㄹㄹㄹㄹㄹㄹㄹㄹㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅇㅇㅇㅇㅇㅇㅇㅇㅇㅇㅇㅇㅇㅇㅇㅇㅇㅇㅇㅇㅇㅇㄴㄴㄴㄴㄴㄴㄴ
            </div>
            
            <div class="row signUp_top_padding">
                <div class="col-md-10">개인정보 취급 방침 동의(필수)</div>
                <div class="sinUp_right"><button>동의하기 ></button></div>
              </div>
              <!-- <div id="myDIV" class="divSignUp" style="overflow:scroll;"> -->
              <div class="divSignUp" style="overflow:scroll;">
                이용ㅇㅇㅇㅇㅇㅇㅇㅇㅇㅇㅇ약ㄲㄲㄲㄲㄲㄲㄲㄲㄲㄲ곽ㄴㄴㄴㄴㄴㄴㄴㄴㄴㄴㄴㄴㄴㄴㄴㄴㄴㄴㄴㄴㄴㄴㄴㅇ미ㅜㄹ머ㅜㅇㅁ우림ㅇㅇㅇㅇㅇㅇㅇㅇㅇㅇㅇㅇㅇㅇㅇㅇㅇㅇㅇㅇㅇㅇㅇㅇㅇㅇㅇ
                ㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅋㅋㅋㅋㅋㅋㅋㅋㅋㅋㅋㅋㅋㅋㅋㅋasdffffffffffffffffffffffffffaㅁㄴㅇㄹㅁㄴㅇㄹㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁ
                ㅁㄴㅇㄹㄹㄹㄹㄹㄹㄹㄹㄹㄹㄹㄹㄹㄹㄹㄹㄹㄹㄹㄹㄹㄹㄹㄹㄹㄹㄹㄹㄹㄹㄹㄹㄹㄹㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁㅁaaaaaaaaaaaaaaaasddddddddddddㄴㄴㄴㄴㄴㄴㄴ
              </div>
              <div class="col-sm-offset-5 signUp_top_padding">
                <!-- <button onclick="display()" class="btn btn-primary"> 다음 단계 > </button> -->
                <button class="btn btn-primary"> 다음 단계 > </button>
              </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { Modal } from 'bootstrap-vue/es/components';

export default {
  data () {
    return {
      form: {
        email: '',
        name: '',
        food: null,
        checked: []
      },
      foods: [
        { text: 'Select One', value: null },
        'Carrots', 'Beans', 'Tomatoes', 'Corn'
      ],
      show: true
    }
  },
  methods: {
    onSubmit (evt) {
      evt.preventDefault();
      alert(JSON.stringify(this.form));
    },
    onReset (evt) {
      evt.preventDefault();
      /* Reset our form values */
      this.form.email = '';
      this.form.name = '';
      this.form.food = null;
      this.form.checked = [];
      /* Trick to reset/clear native browser form validation state */
      this.show = false;
      this.$nextTick(() => { this.show = true });
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
  font-family: 'Noto Sans KR', sans-serif;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}

.btnModal {
  background: none;
  border: none;
}
</style>
