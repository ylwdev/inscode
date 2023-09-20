<template>
  <div>
    用户注册组件
    <Input v-model="form.userName" />
    <Input v-model="form.password" />
    <Button class="ivu-mt" type="primary" @click="register">注册</Button>
  </div>
</template>

<script>
import { ref, computed } from 'vue'
import { Message } from 'view-ui-plus'

export default {
  name: 'ins-register',
  emits: ['registerSuccess'],
  data () {
    return {
      form: {
        userName: '',
        password: ''
      }
    }
  },
  methods: {
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
      this.$emit('registerSuccess', 'login');
    },
  }
}
</script>
