我正在使用Vue开发项目，
目前系统已经内置以下组件:
1.登录组件
组件名：ins-login
作用:登录、注册功能
使用方式: import insLogin from './components/login.vue'
接收参数：
defaultPage：String类型，参数值login或register，默认值是login，该参数表示切换该组件是登录或注册
事件：登陆成功支持回调方法 @loginSuccess 

2.列表组件
组件名：ins-list
作用：一组数据以列表显示，并提供一个查看的功能
使用方式：import insList from './components/login.vue'
事件：点击查看按钮支持回调方法 @view，参数为 item

3.内容详情页组件
组件名： ins-item
作用：展示ins-list组件单独的item信息
使用方式： import insItem from './components/item.vue'
接收参数： 
item: Object对象，接收ins-list组件@view事件返回的item参数
事件: @backToList 点击返回列表页按钮

4.Toolbar组件
组件名：ins-toolbar
作用：给页面头部添加toolbar导航，此组件必须放在页面头部
使用方式： import insToolbar from './components/toolbar.vue'


使用以上组件实现下述需求，要求返回完整代码，不需要解释直接返回完整代码，Markdown格式，需求是：
1. 用户未登录时，展示登录组件，用户可以登录或注册
2. 用户登录后，显示列表页
3. 点击列表页后，显示内容详情
4. 所有功能在一个页面完成
5. 所有组件，使用以上已经实现的组件，不要自己重新写
6. 显示组件展示的时候，列表组件不显示
7. 显示注册组件的时候不要显示登录组件