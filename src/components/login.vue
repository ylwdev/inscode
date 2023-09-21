<template>
  <div>
    <template v-if="currentPage === 'login'">
      用户登录组件
      <Input v-model="userName" />
      <Input v-model="password" />
      <Button class="ivu-mt" type="primary" @click="handleLogin">登录</Button>&nbsp;&nbsp;
      <Button class="ivu-mt" type="primary" @click="toRegister">去注册</Button>
    </template>
    <template v-else-if="currentPage === 'register'">
      用户注册组件
      <Input v-model="form.userName" />
      <Input v-model="form.password" />
      <Button class="ivu-mt" type="primary" @click="register">注册</Button>
    </template>
  </div>
</template>

<script>
import { ref, computed } from 'vue'
import { Message } from 'view-ui-plus'

export default {
  name: 'ins-login-register',
  props: {
    defaultPage: {
      type: String,
      default: 'login'
    }
  },
  data () {
    return {
      currentPage: this.defaultPage,
      userName: '',
      password: '',
      form: {
        userName: '',
        password: ''
      }
    }
  },
  methods: {
    handleLogin() {
      const currentUser = JSON.parse(localStorage.getItem('currentUser'))
      if (!currentUser || currentUser.userName !== this.userName || currentUser.password !== this.password) {
        Message.error('用户名或密码错误')
        return
      }
      localStorage.setItem('loginStatus',true);
      this.$emit('loginSuccess','list')
    },
    toRegister() {
      this.currentPage = 'register'
    },
    register () {
      const { userName, password } = this.form
      if (!userName || !password) {
        Message.error('用户名和密码不能为空');
        return;
      }
      localStorage.setItem('currentUser', JSON.stringify({
        userName,
        password
      }));
      this.currentPage = 'login'
    },
    loginCheck(){
      if(localStorage.getItem('loginStatus')){
        this.$emit('loginSuccess','list')
      };
    }
  },
  mounted(){
    this.loginCheck()
  }
}
</script>
