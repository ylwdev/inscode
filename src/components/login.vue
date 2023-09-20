<template>
  <div>
    用户登录组件
    <Input v-model="userName" />
    <Input v-model="password" />
    <Button class="ivu-mt" type="primary" @click="handleLogin">登录</Button>
  </div>
</template>

<script>
import { ref, computed } from 'vue'
import { Message } from 'view-ui-plus'

export default {
  name: 'ins-login',
  emits: ['loginSuccess'],
  data () {
    return {
      userName: '',
      password: ''
    }
  },
  methods: {
    handleLogin() {
      const currentUser = JSON.parse(localStorage.getItem('currentUser'))
      if (!currentUser || currentUser.userName !== this.userName || currentUser.password !== this.password) {
        Message.error('用户名或密码错误')
        return
      }
      this.$emit('loginSuccess','list')
    }
  }
}
</script>
