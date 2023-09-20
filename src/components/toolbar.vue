<template>
    <div class="toolbar">
        <div class="toolbar-left">
            <img :src="logoUrl" :style="{ height: logoHeight }" />
        </div>
        <div class="toolbar-center">
            <Button v-for="menu in menuList" :key="menu.id" type="text" :style="{ color: menu.color }">{{ menu.name }}</Button>
        </div>
        <div class="toolbar-right">
            <Avatar :size="32" style="margin-right: 10px;" :src="avatarUrl">
            </Avatar>
            <span :style="{ color: userNameColor }">{{ userName }}</span>
        </div>
    </div>
</template>
  
<script>
import { Icon, Button, Avatar } from 'view-ui-plus'

export default {
    name: 'ins-toolbar',
    emits: ['toPage'],
    props: {
        logoUrl: {
            type: String,
            default: "https://file.iviewui.com/view-design-dist/img/logo.362917a9.png"
        },
        logoHeight: {
            type: String,
            default: "40px"
        },
        menuList: {
            type: Array,
            default: () => [
                { id: 1, name: "注册", color: "#1E90FF" },
                { id: 2, name: "登录", color: "#1E90FF" },
                { id: 3, name: "列表", color: "#1E90FF" }
            ]
        },
        avatarUrl: {
            type: String,
            default: "https://dev-file.iviewui.com/avatar_default/avatar"
        },
        userName: {
            type: String,
            default: "张三"
        },
        userNameColor: {
            type: String,
            default: "#1E90FF"
        }
    },
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
    color: #1E90FF;
    /*修改字体颜色为天蓝色*/
    font-size: 14px;
    font-weight: bold;
}

.toolbar-left {
    margin-right: 20px;
}

.toolbar-center {
    display: flex;
    justify-content: flex-start;
    /*修改菜单对齐方式为靠左*/
}

.toolbar-right {
    display: flex;
    align-items: center;
}
</style>
  