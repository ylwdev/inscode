<template>
    <div class="container">
        详情页组件
        <h1> {{ item.title }} </h1>
        <div class="info">
            <p class="time">创建时间：2023年09月20日17:06:57</p>
            <p class="owner">作者：inscode</p>
            <button @click="backToList">Back to List</button>

        </div>
        <p class="content" v-html="item.description"></p>
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
            item:{
                type: Object,
                default: {
                    avatar: 'https://img1.doubanio.com/view/photo/s_ratio_poster/public/p2897210097.webp',
                    title: '奥本海默 Oppenheimer',
                    description: '随着战争阴云笼罩世界上空，各国紧锣密鼓抓紧军事竞赛。为了抢占先机，美国陆军中将莱斯利·格罗夫斯（马特·达蒙 Matt Damon 饰）找到量子力学与核物理学领域的扛鼎人物罗伯特·奥本海默（基里安·墨菲 Cillian Murphy 饰），力荐其担任曼哈顿计划的首席科学家以及洛斯阿拉莫斯国家实验室的总负责人。经过两年争分夺秒的研发，硕大的蘑菇云终于在荒原的上空腾起，也宣告着绞肉机一般的二战即将落下帷幕。',
                    url: 'https://movie.douban.com/subject/35593344/?from=showing'
                }
            }
        },
        data () {
            return {
                
            }
        },
        methods: {
            backToList() {
                this.$emit('backToList')
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