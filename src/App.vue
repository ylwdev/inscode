

<template>
  <div>
    <i-login v-if="!isLogin" name="inscodeName" icon="https://a.png" @loginSuccess="handleLoginSuccess" />
    <div v-if="isLogin" >登陆成功</div>
  </div>
</template>

<script>
import iLogin from 'view-ui-plus'

export default {
  components: {
    iLogin
  },
  data() {
    return {
      isLogin: false
    }
  },
  methods: {
    handleLoginSuccess() {
      this.isLogin = true
    }
  }
}
</script>