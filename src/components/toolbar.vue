<template>
    <div class="toolbar">
      <div class="toolbar-left">
        <img src="https://file.iviewui.com/view-design-dist/img/logo.362917a9.png" style="height: 40px" />
      </div>
      <div class="toolbar-center">
        <Button type="text" style="color: #1E90FF;">菜单 1</Button>
        <Button type="text" style="color: #1E90FF;">菜单 2</Button>
        <Button type="text" style="color: #1E90FF;">菜单 3</Button>
      </div>
      <div class="toolbar-right">
        <Avatar :size="32" style="margin-right: 10px;" src="https://dev-file.iviewui.com/avatar_default/avatar"></Avatar>
        <span style="color: #1E90FF;">张三</span>
      </div>
    </div>
  </template>
  
  <script>
  import {Icon, Button,Avatar} from 'view-ui-plus'
  
  export default {
    name: 'i-toolbar',
    components: {
      Icon,
      Button,
      Avatar
    },
    props: {},
    data() {
      return {
        data: []
      }
    }
  }
  </script>
  <style>
  .toolbar {
    height: 64px;
    padding: 0 20px;
    background-color: #f8f8f9;
    display: flex;
    align-items: center;
    justify-content: space-between;
    color: #1E90FF; /*修改字体颜色为天蓝色*/
    font-size: 14px;
    font-weight: bold;
  }
  
  .toolbar-left {
    margin-right: 20px;
  }
  
  .toolbar-center {
    display: flex;
    justify-content: flex-start; /*修改菜单对齐方式为靠左*/
  }
  
  .toolbar-right {
    display: flex;
    align-items: center;
  }
  </style>
  