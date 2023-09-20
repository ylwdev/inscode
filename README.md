## 推荐的IDE设置

[VSCode](https://code.visualstudio.com/) + [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar) (and disable Vetur) + [TypeScript Vue Plugin (Volar)](https://marketplace.visualstudio.com/items?itemName=Vue.vscode-typescript-vue-plugin).

## 自定义配置

请参阅 [[Vite配置参考](https://vitejs.dev/config/).

## 项目设置

```sh
npm install
```

### 在开发环境中启动和热更新

```sh
npm run dev
```

### 编译用于生产环境

```sh
npm run build
```

我正在使用Vue开发项目，
目前系统已经内置以下组件:
1.登录组件
组件名：i-login
作用:登录注册
使用方式: import iLogin from 'inscode'
事件：登陆成功支持回调方法 @loginSuccess
接收参数： 
name 登录框名称
icon 登录框图标

2.列表组件
组件名：i-list
作用：一组数据以列表显示，并提供一个查看的功能
使用方式：import insList from 'inscode'
事件：点击查看按钮支持回调方法 @view，参数为 url

3.用户详情页组件
组件名： user-detail
作用：用户信息展示
使用方式： import userDetail from 'inscode'

使用以上组件实现下述需求，要求返回完整代码，不需要解释直接返回完整代码，Markdown格式，需求是：
实现一个登录功能，登录框名称是inscodeName,icon使用https://a.png，登陆成功跳转到列表页