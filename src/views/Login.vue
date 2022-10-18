<template>
  <div class="bg">
<!--  登录主界面-->
    <el-form ref="loginForm" :model="loginForm" :rules="rules" class="loginForm">
      <h3 class="loginTitle">管理员系统登录</h3>
      <!--用户名输入框-->
      <el-form-item prop="username">
        <el-input v-model="loginForm.username"
                  auto-complete="false"
                  placeholder="请输入用户名"
                  type="text">
        </el-input>
      </el-form-item>
      <!--密码输入框-->
      <el-form-item prop="password">
        <el-input v-model="loginForm.password"
                  auto-complete="false"
                  placeholder="请输入密码"
                  type="password">
        </el-input>
      </el-form-item>
      <!--角色选择框-->
      <el-form-item>
        <el-radio style="position: relative;left: -40px" v-model="type" label="systemAdmin">系统管理员</el-radio>
        <el-radio style="position: relative;left: 50px" v-model="type" label="dormitoryAdmin">宿舍管理员</el-radio>
      </el-form-item>
      <!--功能区-->
      <el-button style="width: 100%" type="primary" @click="submitLogin" :loading="loginLoad">登录</el-button>
    </el-form>
  </div>
</template>

<script>

import 'nprogress/nprogress.css'

export default {
  name: "Login",
  data() {
    return {
      captchaUrl: '',
      loginForm: {
        username: 'admin',
        password: '123456'
      },
      type: 'systemAdmin',
      loginLoad: false,
      rules: {
        username: [{required: true, message: '请输入用户名', trigger: 'blur'}],
        password: [{required: true, message: '请输入密码', trigger: 'blur'}],
      }
    }
  },
  methods: {
    
  }
}
</script>

<style scoped>
.bg{
  width: 100%;
  height: 100%;
  position: absolute;
  background: #409EFF;
  background-image: url("../assets/wallhaven-9m61m1.png");
}

.loginForm {
  border-radius: 15px;
  background-clip: padding-box;
  margin: 180px auto;
  width: 350px;
  padding: 15px 35px 15px 35px;
  background: white;
  border: 1px solid #eaeaea;
}

.loginTitle {
  margin: 0 auto 40px auto;
  text-align: center;
}
</style>
