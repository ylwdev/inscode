<template>
  <div class="ivu-p">
    <Alert>
      当前 Vue 版本为 {{ vueVersion }}，View UI Plus 版本为 {{ version }}
    </Alert>
  </div>
  <div>公共toolbar</div>

  <div v-if="currentPage === 'register'">
    用户注册页
    <Input v-model="userName" />
    <Input v-model="password" />
    <Button class="ivu-mt" type="primary" @click="register">注册</Button>
  </div>

  <div v-if="currentPage === 'login'">
    用户注册页
    <Input v-model="userName" />
    <Input v-model="password" />
    <Button class="ivu-mt" type="primary" @click="login">登录</Button>
  </div>

  <div v-if="currentPage === 'list'">列表页</div>
  <div v-if="currentPage === 'detail'">详情页</div>
</template>
<script setup>
import { ref, version as vueVersion } from 'vue' // 从 Vue 中导入 ref 和 vueVersion
import { version, Message } from 'view-ui-plus' // 从 view-ui-plus 中导入 version 和 Message


let currentPage = "register";

function register(){
  currentPage="login";
}
function login(){
  currentPage="list";
}

</script>

<style></style>