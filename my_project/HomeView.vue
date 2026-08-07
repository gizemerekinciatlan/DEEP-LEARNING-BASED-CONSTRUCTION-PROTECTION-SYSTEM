<template>
  <div class="login">
    <div class="main-box">
      <!-- <div :class="['container', 'container-register', { 'is-txl': isLogin }]">
        <form>
          <h2 class="title">Create Account</h2>
          <input class="form__input" type="text" placeholder="Name" />
          <input class="form__input" type="text" placeholder="Email" />
          <input class="form__input" type="password" placeholder="Password" />
          <div class="primary-btn">Register Now</div>
        </form>
      </div> -->
      <div
        :class="['container', 'container-login', { 'is-txl is-z200': isLogin }]"
      >
        <form>
          <h2 class="title">Welcome to the Manage System !</h2>
          <div class="username">
            <span class="iconfont">&#xe7ae;
            </span>
            <span>username&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
                  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
                  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
                  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
                  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
                  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
                  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
                  &nbsp;&nbsp;&nbsp;
            </span>
          </div>
          <input class="form__input" type="text" placeholder="Email" />
          <div class="password">
            <span class="iconfont">&#xe66b;
            </span>
            <span>password&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
                  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
                  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
                  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
                  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
                  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
                  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
                  &nbsp;&nbsp;&nbsp;
            </span>
          </div>
          <input class="form__input" type="password" placeholder="Password" />
          <div class="primary-btn" @click="login">Sign In</div>
        </form>
      </div>
      <!-- <div :class="['switch', { login: isLogin }]">
        <div class="switch__circle"></div>
        <div class="switch__circle switch__circle_top"></div>
        <div class="switch__container">
          <h2>{{ isLogin ? 'Hello Manager' : 'Welcome Back' }}</h2>
          <p>
            {{
              isLogin
                ? 'Enter your personal details and start journey with us'
                : 'To keep connected with us please login with your personal info'
            }}
          </p>
          <div class="primary-btn" @click="isLogin = !isLogin">
            {{ isLogin ? 'Register now' : 'Sign In' }}
          </div>
        </div>
      </div> -->
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'HomeView',
  components: {
    HelloWorld
  },
  data() {
    return {
      isLogin: false,
      loginForm: {
        email: '',
        password: '',
      },
      registerForm: {
        name: '',
        email: '',
        password: '',
      },
    }
  },
  methods: {
    login(){
      this.$router.push('/index')
    },
    register() {},
  }
}
</script>

<style lang="scss" scoped>
@font-face {
  font-family: "iconfont"; /* Project id 3867447 */
  src: url('//at.alicdn.com/t/c/font_3867447_wnbmor14fd.woff2?t=1674055509160') format('woff2'),
       url('//at.alicdn.com/t/c/font_3867447_wnbmor14fd.woff?t=1674055509160') format('woff'),
       url('//at.alicdn.com/t/c/font_3867447_wnbmor14fd.ttf?t=1674055509160') format('truetype');
}

.iconfont {
  font-family: "iconfont" !important;
  font-size: 16px;
  font-style: normal;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

.icon-3701mima:before {
  content: "\e66b";
}

.icon-user:before {
  content: "\e7ae";
}
.password {
  margin-top: 5px;
}
.login {
  height: 100vh;
    background: url('../assets/IMG_5991.JPG') center center fixed
      no-repeat rgba(0,0,0,0.5);
    background-size: cover;
}
.main-box {
  position: absolute;
  width: 38%;
  min-width: 38%;
  min-height: 500px;
  height: 500px;
  padding: 25px;
  background-color: #bec1c4;
  box-shadow: 10px 10px 10px #bcc3ce;
  border-radius: 12px;
  overflow: hidden;
  top: 100px;
  left: 50%;
  .container {
    display: flex;
    justify-content: center;
    align-items: center;
    position: absolute;
    top: 0;
    width: 600px;
    height: 100%;
    padding: 25px;
    background-color: #ecf0f3;
    transition: all 1.25s;
    form {
      display: flex;
      justify-content: center;
      align-items: center;
      flex-direction: column;
      width: 100%;
      height: 100%;
      color: #a0a5a8;
      .title {
        font-size: 30px;
        font-weight: 500;
        color: #181818;
        padding-bottom: 48px;
      }
      .text {
        margin-top: 30px;
        margin-bottom: 12px;
      }
      .form__input {
        width: 350px;
        height: 40px;
        margin: 4px 0;
        padding-left: 25px;
        font-size: 13px;
        letter-spacing: 0.15px;
        border: none;
        outline: none;
        // font-family: 'Montserrat', sans-serif;
        background-color: #ecf0f3;
        transition: 0.25s ease;
        border-radius: 8px;
        box-shadow: 4px 4px 6px 0 rgb(255 255 255 / 50%);
        &::placeholder {
          color: #a0a5a8;
        }
      }
    }
  }
  .container-register {
    z-index: 100;
    left: calc(100% - 600px);
  }
  .container-login {
    left: calc(100% - 600px);
    z-index: 0;
  }
  .is-txl {
    left: 0;
    transition: 1.25s;
    transform-origin: right;
  }
  .is-z200 {
    z-index: 200;
    transition: 1.25s;
  }
  .switch {
    display: flex;
    justify-content: center;
    align-items: center;
    position: absolute;
    top: 0;
    left: 0;
    height: 100%;
    width: 400px;
    padding: 50px;
    z-index: 200;
    transition: 1.25s;
    background-color: #ecf0f3;
    overflow: hidden;
    box-shadow: 4px 4px 10px #d1d9e6, -4px -4px 10px #f9f9f9;
    color: #a0a5a8;
    .switch__circle {
      position: absolute;
      width: 500px;
      height: 500px;
      border-radius: 50%;
      background-color: #ecf0f3;
      box-shadow: inset 8px 8px 12px #d1d9e6, inset -8px -8px 12px #f9f9f9;
      bottom: -60%;
      left: -60%;
      transition: 1.25s;
    }
    .switch__circle_top {
      top: -30%;
      left: 60%;
      width: 300px;
      height: 300px;
    }
    .switch__container {
      display: flex;
      justify-content: center;
      align-items: center;
      flex-direction: column;
      position: relative;
      width: 526px;
      left: -48px;
      padding: 50px;
      transition: 1.25s;
      h2 {
        font-size: 34px;
        font-weight: 700;
        line-height: 3;
        color: #181818;
      }
      p {
        font-size: 14px;
        letter-spacing: 0.25px;
        text-align: center;
        line-height: 1.6;
      }
    }
  }
  .login {
    left: calc(100% - 400px);
    .switch__circle {
      left: 0;
    }
  }
  .primary-btn {
    width: 180px;
    height: 50px;
    border-radius: 25px;
    margin-top: 50px;
    text-align: center;
    line-height: 50px;
    font-size: 14px;
    letter-spacing: 2px;
    background-color: #4b70e2;
    color: #f9f9f9;
    cursor: pointer;
    box-shadow: 8px 8px 16px #d1d9e6, -8px -8px 16px #f9f9f9;
    &:hover {
      box-shadow: 4px 4px 6px 0 rgb(255 255 255 / 50%),
        -4px -4px 6px 0 rgb(116 125 136 / 50%),
        inset -4px -4px 6px 0 rgb(255 255 255 / 20%),
        inset 4px 4px 6px 0 rgb(0 0 0 / 40%);
    }
  }
}
</style>


