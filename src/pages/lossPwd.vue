<template>
  <div @touchmove.prevent>
    <m-header :title="title"></m-header>

    <div class="maincontainer">
      <div class="content">
        <form @submit.prevent="submit">
          <div>
            <div class="top">
              <!-- <input type="text" disabled="disabled" style="color:#ccc;" class="input1" v-model="user.num1" maxlength="11" placeholder="请输入正确的手机号码" @input="inputFuction"> -->
              <div class="main" style="margin-top:0px;">
                              <img class="line1" src="../../static/images/zuo.png">
                              </img>
                              <div class="line21" style="width:50%;">
                                <input class="line22" type="text" disabled="disabled" style="color:#ccc;" v-model="user.num1" maxlength="11" placeholder="请输入正确的手机号码" @input="inputFuction">
                                </input>
                              </div>
                              <img class="line3" src="../../static/images/you.png">
                              </img>
              </div>
              <el-button class="btn" type="primary" @click="ResetPwdSMS">获取验证码</el-button>
            </div>
            <div class="bottom">
              <!-- <input class="input" v-model="user.verify" type="text" maxlength="20" placeholder="请输入验证码" @input="inputFuction">
              <input class="input" v-model="user.newpwd1" type="password" maxlength="18" placeholder="请输入6-18位新密码" @input="inputFuction">
              <input class="input" v-model="user.newpwd2" type="password" maxlength="18" placeholder="确认输入" @input="inputFuction"> -->
              <div class="main">
                  <img class="line1" src="../../static/images/zuo.png">
                  </img>
                  <div class="line21">
                    <input class="line22" v-model="user.verify" type="text" maxlength="20" placeholder="请输入验证码" @input="inputFuction">
                    </input>
                  </div>
                  <img class="line3" src="../../static/images/you.png">
                  </img>
              </div>
              <div class="main">
                  <img class="line1" src="../../static/images/zuo.png">
                  </img>
                  <div class="line21">
                    <input class="line22" v-model="user.newpwd1" type="password" maxlength="18" placeholder="请输入6-18位新密码" @input="inputFuction">
                    </input>
                  </div>
                  <img class="line3" src="../../static/images/you.png">
                  </img>
              </div>
              <div class="main">
                  <img class="line1" src="../../static/images/zuo.png">
                  </img>
                  <div class="line21">
                    <input class="line22" v-model="user.newpwd2" type="password" maxlength="18" placeholder="确认输入" @input="inputFuction">
                    </input>
                  </div>
                  <img class="line3" src="../../static/images/you.png">
                  </img>
              </div>
            </div>
          </div>
          <el-button v-if="disabled" :disabled="disabled" class="btnEnable" type="primary" native-type="submit">确认修改</el-button>
          <el-button v-else :disabled="disabled" class="btnDefault" type="primary" native-type="submit">确认修改</el-button>
        </form>
      </div>
    </div>
  </div>
</template>

<style lang="less" scoped>
.main {
    display: flex;
    flex-direction: row;
    // margin: 2px;
    line-height: 38px;
    color: #fffde4;
    position: relative;
    margin-top: 10%;
    //   background: red;
    .line1 {
      background-repeat: no-repeat;
      height: 40px;
      width: 19px;
    }
    .line21 {
      background: url("../../static/images/zhong.png");
      background-repeat: repeat;
      font-size: 12px;
      height: 40px;
      width: 225px;
      color: white;
    //   padding:0px -5px 0px -5px;
    }
    .line22 {
        outline: none;
      font-size: 12px;
      height: 40px;
      width: 225px;
      color: white;
      // padding-left: 15px;
      background: rgba(255,255,255,0);
    //   padding:0px -5px 0px -5px;
    }
    
    .line3 {
      background-repeat: no-repeat;
      height:40px;
      width: 19px;
    }
}

#bundle {
  .juzhong {
    display: -webkit-flex;
    display: flex;
    -webkit-align-items: center;
    align-items: center;
    -webkit-justify-content: center;
    justify-content: center;
  }
}

::-webkit-input-placeholder {
  /* WebKit browsers */
  color: RGB(229, 164, 153);
  font-size: 12px;
}

.maincontainer {
  background-image: url('../../static/images/login/Passwordbg.png');
  background-repeat: no-repeat;
  background-size: 100% 100%;
  width: 100%;
  height: 100%;
  position: absolute;
  top: 0px;
  .content {
    #bundle>.juzhong;
    margin-top: 20%;
    flex-direction: column;
    .top {
      margin-top: 20%;
      display: flex;
      flex-direction: row;
      .input1 {
        outline: none;
        background-color: transparent;
        background-image: url('../../static/images/login/a4.png');
        background-repeat: no-repeat;
        background-size: 100% 100%;
        height: 44px;
        line-height: 44px;
        width: 100%;
        padding-left: 10px;
        font-size: 12px;
        color: white;
      }
      .btn {
        // #bundle>.juzhong;
        margin-left: -70px;
        height: 40px;
        width: 40%;
        border-radius: 5px;
        background-color: RGB(251, 230, 231);
        border: 0;
        color: red;
        font-size: 12px;
        align-content: center;
      }
    }
    .bottom {
      display: flex;
      flex-direction: column;
      .input {
        outline: none;
        margin-top: 10%;
        background-color: transparent;
        background-image: url('../../static/images/login/a2.png');
        background-repeat: no-repeat;
        background-size: 100% 100%;
        height: 44px;
        line-height: 44px;
        width: 100%;
        padding-left: 10px;
        font-size: 12px;
        color: white;
      }
    }
    .btnDefault {
      margin-top: 30px;
      height: 40px;
      width: 100%;
      border-radius: 40px;
      background-color: RGB(251, 230, 231);
      border: 0;
      color: red;
      font-size: 18px;
    }
    .btnEnable {
      margin-top: 30px;
      height: 40px;
      width: 100%;
      border-radius: 40px;
      background-color: RGB(240, 144, 156);
      border: 0;
      color: #fff;
      font-size: 18px;
    }
  }
}
</style>


<script>
import mHeader from '../components/hearder/Hearder';
import sha256 from '../util/sha256'
import { Toast, MessageBox } from "mint-ui";
export default {
  name: 'lossPwdVC',
  data() {
    return {
      title: {
        text: "忘记密码",
        showBack: true
      },
      user: {
        num: localStorage.phoneNum,
        num1: "",
        verify: '',
        newpwd1: '',
        newpwd2: '',
      },
      disabled: true,
    };
  },

  mounted(){
    var str = "*******";
    for(var i = 0; i < this.user.num.length ; i++){
      if(i > 6){
        str = str + this.user.num[i];
      }
    }
    this.user.num1 = str;
  },

  methods: {
    
    inputFuction() {
      if (this.user.num.length > 0 && this.user.verify.length > 0 && this.user.newpwd1.length > 0 && this.user.newpwd2.length > 0) {
        this.disabled = false;
      } else {
        this.disabled = true;
      }
    },
    ResetPwdSMS() {

      let data = new FormData();
      data.append('Action', 'GetVCode');
      data.append('SID', this.user.sid);

      this.$http.post(this.global.url, data).then(res => {

        if (res) {
          console.log(res.data.Data);

          localStorage.vcode = res.data.Data;
          let data = new FormData();
          data.append('Action', 'ResetPwdSMS');
          data.append('SID', localStorage.sid);
          data.append('Mobile', this.user.num);
          data.append('AppType', this.global.AppType);
          data.append('VCode', res.data.Data);

          this.$http.post(this.global.url, data).then(res1 => {

            if (res1) {
              console.log(res1);
            }

          }).catch(error1 => {
            console.log(error1);
          })

        }

      }).catch(error => {
        console.log(error);
      })


    },



    submit: function(event) {

      // var formData = JSON.stringify(this.user); // 这里才是你的表单数据
      // console.log(formData);
      if (this.user.newpwd1 == this.user.newpwd2) {
        this.user.newpwd1 = sha256.sha256(this.user.newpwd1).toUpperCase();
        // 请求数据
        let data = new FormData();
        data.append('Action', 'ResetPwd2');
        data.append('Account', localStorage.Username);
        data.append('SID', localStorage.sid);
        data.append('Mobile', this.user.num);
        data.append('SMSCode', this.user.verify);
        data.append('Pwd', this.user.newpwd1);
        data.append('AppType', this.global.AppType);
        this.$http.post(this.global.url, data).then(res => {
          console.log(res);
          if (res.data.Code == 'Suc') {
            this.$router.push({
              path: '/login'
            })
          }
        }).catch(error => {
          console.log(error);
        })
      } else {
        MessageBox({
          title: '提示',
          message: '两次输入密码不同，请重新输入',
          showCancelButton: false,
        })
      }

    }
  },
  components: {
    mHeader
  },
}
</script>