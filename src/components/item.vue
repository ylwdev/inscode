<template>
    <div class="container">
        详情页组件
        <h1> {{ title }} </h1>
        <div class="info">
            <p class="time">创建时间：{{ create_time }}</p>
            <p class="owner">作者：{{ owner }}</p>
        </div>
        <p class="content" v-html="content"></p>
    </div>
</template>
<script>
const content = 
`InsCode 为每位开发者提供了免费的 2 核/4 GB 云端开发环境。
InsCode 的 Cloud IDE 是运行于浏览器的集成开发环境（IDE），开发者只需要浏览器，有网络环境，就可以随时随地写代码，不用下载安装，不受硬件、环境的影响。
InsCode 的 Cloud IDE 底层基于 VSCode 开发，使用体验与桌面版 VS Code 几乎一致，提供了高效的文件搜索、Git 版本控制、Debug 调试、数据库、终端、在线预览等功能。
`
    export default {
        name: 'ins-item',
        props: {
            title: {
                type: String,
                default: '文章详情页'
            },
            create_time: {
                type: String,
                default: '2023-09-20 00:00:00'
            },
            owner: {
                type: String,
                default: 'inscode'
            },
            content: {
                type: String,
                default: content
            },

        },
        data () {
            return {
                
            }
        }
    }
</script>
<style>
.container {
    min-width: 200px;
    max-width: 800px;
    padding: 16px;
    margin: auto;
    font-family: "Chinese Quotes", "Inter var", Inter, ui-sans-serif, system-ui, -apple-system, "system-ui", "Segoe UI", Roboto, "Helvetica Neue", Helvetica, Arial, "Noto Sans", sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji";
}

h1 {
    letter-spacing: -.02em;
    line-height: 40px;
    font-size: 32px;
    color:rgb(52, 81, 178);
}
.info {
    margin: 16px 0px;
    color:#7687a9;
}


.content {
    /* color: rgb(60, 60, 67); */
    line-height: 24px;
    white-space: pre-wrap;
}
</style>