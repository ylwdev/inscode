<template>
  <div>
    <ins-toolbar></ins-toolbar>
    <div v-if="!isLoggedIn">
      <ins-login @loginSuccess="loginSuccess" @toRegisterPage="showRegister"></ins-login>
      <!-- <ins-register v-if="isRegisterShown" @registerSuccess="registerSuccess"></ins-register> -->
    </div>
    <div v-else>
      <ins-list :items="items" @view="viewItem"></ins-list>
      <ins-item v-if="isItemShown" :item="selectedItem" @backToList="backToList"></ins-item>
    </div>
  </div>
</template>

<script>
import insLogin from './components/login.vue'
import insRegister from './components/register.vue'
import insList from './components/list.vue'
import insItem from './components/item.vue'
import insToolbar from './components/toolbar.vue'

export default {
  components: {
    insLogin,
    insRegister,
    insList,
    insItem, 
    insToolbar
  },
  data() {
    return {
      isLoggedIn: false,
      isRegisterShown: false,
      items: [
        {title: 'Item 1', content: 'Item 1 content'},
        {title: 'Item 2', content: 'Item 2 content'},
        {title: 'Item 3', content: 'Item 3 content'}
      ],
      isItemShown: false,
      selectedItem: null
    }
  },
  methods: {
    loginSuccess() {
      this.isLoggedIn = true
    },
    showRegister() {
      this.isRegisterShown = true
    },
    registerSuccess() {
      this.isRegisterShown = false
    },
    viewItem(item) {
      this.isItemShown = true
      this.selectedItem = item
    },
    backToList() {
      this.isItemShown = false
      this.selectedItem = null
    }
  }
}
</script>
