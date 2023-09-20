<template>
  <div class="ivu-p">
    <Alert>
      当前 Vue 版本为 {{ vueVersion }}，View UI Plus 版本为 {{ version }}
    </Alert>
  </div>
  <div>公共 toolbar</div>

  <div v-if="currentPage === 'register'">
    用户注册
    <Input v-model="userName" />
    <Input v-model="password" />
    <Button class="ivu-mt" type="primary" @click="register">注册</Button>
  </div>

<<<<<<< HEAD
<template>
  <div>
    <iItem />
=======
  <div v-if="currentPage === 'login'">
    用户登录
    <Input v-model="userName" />
    <Input v-model="password" />
    <Button class="ivu-mt" type="primary" @click="login">登录</Button>
>>>>>>> 75d860539d73fa062610cef037dbe3a9b249332d
  </div>

  <div v-if="currentPage === 'list'">列表页</div>
  <div v-if="currentPage === 'detail'">详情页</div>
  <ins-list></ins-list>
</template>

<<<<<<< HEAD
<script>
import iItem from './components/item.vue'

export default {
  components: {
    iItem
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
=======
<script setup>
import { ref, computed, version as vueVersion } from 'vue'
import { version, Message } from 'view-ui-plus'
import insList from './components/list.vue'

let currentPage = ref(localStorage.getItem('currentUser') ? 'list' : 'register');
let userName = ref('');
let password = ref('');

function register() {
  if (!userName.value || !password.value) {
    Message.error('用户名和密码不能为空');
    return;
>>>>>>> 75d860539d73fa062610cef037dbe3a9b249332d
  }
  localStorage.setItem('currentUser', JSON.stringify({
    userName: userName.value,
    password: password.value
  }));
  currentPage.value = 'login';
}

function login() {
  const currentUser = JSON.parse(localStorage.getItem('currentUser'));
  if (!currentUser || currentUser.userName !== userName.value || currentUser.password !== password.value) {
    Message.error('用户名或密码错误');
    return;
  }
  currentPage.value = 'list';
}

const currentUser = computed(() => JSON.parse(localStorage.getItem('currentUser')));

</script>

<style></style> 
