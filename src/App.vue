<template>
  <div>
    <ins-toolbar title="My App">
      <span slot="right" v-if="isLogin">欢迎，{{username}}！ <a href="" @click.prevent="handleLogout">退出</a></span>
    </ins-toolbar>
    <div v-if="!isLogin">
      <ins-login @loginSuccess="handleLoginSuccess" @toRegisterPage="openRegister"></ins-login>
      <ins-register v-show="showRegister" @registerSuccess="handleRegisterSuccess" @toLoginPage="showLogin"></ins-register>
    </div>
    <div v-else>
      <ins-list :data="dataList" @view="showItem"></ins-list>
      <ins-item v-if="showItemDetail" :item="selectedItem" @backToList="showList"></ins-item>
    </div>
  </div>
</template>

<script>
import insLogin from './components/login.vue';
import insList from './components/list.vue';
import insItem from './components/item.vue';
import insToolbar from './components/toolbar.vue';
import insRegister from './components/register.vue';

export default {
  name: 'MyApp',
  components: {
    insLogin,
    insList,
    insItem,
    insToolbar,
    insRegister,
  },
  data() {
    return {
      isLogin: false,
      dataList: [], // 假设数据项只有一个字段 content
      showRegister: false,
      showItemDetail: false,
      selectedItem: {},
      username: '',
    };
  },
  methods: {
    handleLoginSuccess(username) {
      this.isLogin = true;
      this.username = username;
      this.dataList = [{ content: '项目1' }, { content: '项目2' }, { content: '项目3' }];
    },
    handleRegisterSuccess() {
      this.showRegister = false;
    },
    openRegister() {
      this.showRegister = true;
    },
    showLogin() {
      this.showRegister = false;
    },
    handleLogout() {
      this.isLogin = false;
      this.username = '';
    },
    showItem(item) {
      this.selectedItem = item;
      this.showItemDetail = true;
    },
    showList() {
      this.showItemDetail = false;
    },
  },
};
</script>
 
