<template>
  <div class="verify-phone-container">
    <el-form class="login-form" autoComplete="on" :model="phoneNumberForm" :rules="phoneNumberRules" ref="phoneNumberForm" label-position="left">
      <div class="title-container">
        <h3 class="title">美匠</h3>
      </div>
      <el-form-item prop="password">
        <span class="svg-container">
          <svg-icon icon-class="password" />
        </span>
        <el-input name="password" @keyup.enter.native="handleLogin" v-model="phoneNumberForm.phoneNumber" autoComplete="on" placeholder="请输入手机号码" />
      </el-form-item>

      <el-form-item prop="password">
        <span class="svg-container">
          <svg-icon icon-class="password" />
        </span>
        <el-input name="password" @keyup.enter.native="handleLogin" v-model="phoneNumberForm.code" autoComplete="on" placeholder="请输入验证码" />
        <el-button type="primary">获取验证码</el-button>
      </el-form-item>

      <el-button type="primary" style="width:100%;margin-bottom:30px;" :loading="loading" @click.native.prevent="handleLogin">下一步</el-button>
      <div class="back">
        <router-link :to="{ path: 'login' }">
          <span>返回</span>
        </router-link>
      </div>
    </el-form>
  </div>
</template>

<script>
export default {
  name: 'login',
  data () {
    const validatePhoneNumber = (rule, value, callback) => {
      console.log(this.passwrodForm)
      console.log(value)
      if (!value) {
        callback(new Error('用户名不能为空'))
      } else {
        callback()
      }
    }
    const validateCode = (rule, value, callback) => {
      if (value.length < 6) {
        callback(new Error('密码长度不能少于五位'))
      } else {
        callback()
      }
    }
    return {
      phoneNumberForm: {
        phoneNumber: '',
        code: ''
      },
      loading: false,
      phoneNumberRules: {
        newPassword: [{ required: true, trigger: 'blur', validator: validatePhoneNumber }],
        reNewPassword: [{ required: true, trigger: 'blur', validator: validateCode }]
      }
    }
  },
  methods: {
    handleLogin () {
      this.$router.push({ path: 'modifyPassword' })
    }
  }
}
</script>

<style rel="stylesheet/scss" lang="scss">
$bg:#2d3a4b;
$light_gray:#eee;

/* reset element-ui css */
.verify-phone-container {
  .el-input {
    display: inline-block;
    height: 47px;
    width: 66%;
    input {
      background: transparent;
      border: 0px;
      -webkit-appearance: none;
      border-radius: 0px;
      padding: 12px 5px 12px 15px;
      color: $light_gray;
      height: 47px;
      &:-webkit-autofill {
        -webkit-box-shadow: 0 0 0px 1000px $bg inset !important;
        -webkit-text-fill-color: #fff !important;
      }
    }
  }
  .el-form-item {
    border: 1px solid rgba(255, 255, 255, 0.1);
    background: rgba(0, 0, 0, 0.1);
    border-radius: 5px;
    color: #454545;
  }
}
</style>

<style rel="stylesheet/scss" lang="scss" scoped>
$bg: #2d3a4b;
$dark_gray: #889aa4;
$light_gray: #eee;

.verify-phone-container {
  position: fixed;
  top: 0;
  left: 0;
  height: 100%;
  width: 100%;
  z-index: 10;
  .login-form {
    position: absolute;
    left: 0;
    right: 0;
    width: 520px;
    padding: 35px 35px 15px 35px;
    margin: 120px auto;
  }
  .tips {
    font-size: 14px;
    color: #fff;
    margin-bottom: 10px;
    span {
      &:first-of-type {
        margin-right: 16px;
      }
    }
  }
  .svg-container {
    padding: 6px 5px 6px 15px;
    color: $dark_gray;
    vertical-align: middle;
    width: 30px;
    display: inline-block;
    &_login {
      font-size: 20px;
    }
  }
  .title-container {
    position: relative;
    .title {
      font-size: 26px;
      font-weight: 400;
      color: $light_gray;
      margin: 0px auto 40px auto;
      text-align: center;
      font-weight: bold;
    }
    .set-language {
      color: #fff;
      position: absolute;
      top: 5px;
      right: 0px;
    }
  }
  .show-pwd {
    position: absolute;
    right: 10px;
    top: 7px;
    font-size: 16px;
    color: $dark_gray;
    cursor: pointer;
    user-select: none;
  }
  .thirdparty-button {
    position: absolute;
    right: 35px;
    bottom: 28px;
  }
  .back {
    text-align: right;
    font-size: 12px;
    color: #fff;
    cursor: pointer;
  }
}
</style>
