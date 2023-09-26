<template>
  <div>
    <ins-toolbar></ins-toolbar>
    <ins-login v-if="!isLogin" @loginSuccess="handleLoginSuccess" :defaultPage="'login'"></ins-login>
    <ins-list v-if="isLogin && !showItem" @view="handleView"></ins-list>
    <ins-item v-if="isLogin && showItem" @backToList="handleBackToList"></ins-item>
  </div>
</template>

<script>
import insLogin from './components/login.vue'
import insList from './components/list.vue'
import insItem from './components/item.vue'
import insToolbar from './components/toolbar.vue'

export default {
  name: 'app',
  components: {
    insLogin,
    insList,
    insItem,
    insToolbar
  },
  data() {
    return {
      isLogin: false,
      showItem: false
    }
  },
  methods: {
    handleLoginSuccess() {
      this.isLogin = true
    },
    handleView(item) {
      this.showItem = true
    },
    handleBackToList() {
      this.showItem = false
    }
  }
}
</script>
