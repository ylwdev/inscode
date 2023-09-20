<template>
  <div class="ivu-p">
    <Alert>
      当前 Vue 版本为 {{ vueVersion }}，View UI Plus 版本为 {{ version }}
    </Alert>
  </div>
  <div>公共 toolbar</div>

  <ins-register v-if="currentPage=== 'register'" @registerSuccess="changePage"></ins-register>
  <ins-login v-if="currentPage=== 'login'" @loginSuccess="changePage"></ins-login>

  <div v-if="currentPage === 'detail'">详情页</div>
  <ins-list v-if="currentPage === 'list'"></ins-list>
</template>

<script setup>
import { ref, computed, version as vueVersion } from 'vue'
import { version, Message } from 'view-ui-plus'
import insList from './components/list.vue'
import insRegister from './components/register.vue'
import insLogin from './components/login.vue'

let currentPage = ref(localStorage.getItem('currentUser') ? 'list' : 'register');




function changePage(pageName){
  console.log("changePage:",pageName)
  currentPage.value = pageName;
}

const currentUser = computed(() => JSON.parse(localStorage.getItem('currentUser')));

</script>

<style></style> 