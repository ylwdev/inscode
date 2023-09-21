<template>
  <div>
    <ins-toolbar></ins-toolbar>
    
    <div v-if="!isLogin">
      <ins-login @loginSuccess="handleLoginSuccess"></ins-login>
    </div>
    
    <div v-if="isLogin && !showList">
      <ins-item @backToList="handleBackToList" :item="selectedItem"></ins-item>
    </div>
    
    <div v-if="isLogin && showList">
      <ins-list @view="handleView"></ins-list>
    </div>
    
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
      selectedItem: null,
      showList: true
    }
  },
  methods: {
    handleLoginSuccess() {
      this.isLogin = true
      this.showList = true
    },
    handleView(item) {
      this.selectedItem = item
      this.showList = false
    },
    handleBackToList() {
      this.selectedItem = null
      this.showList = true
    }
  }
}
</script>
