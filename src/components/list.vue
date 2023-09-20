<template>
    <List>
        <ListItem v-for="(item, index) in data" :key="index">
            <ListItemMeta
                :avatar="item.avatar"
                :title="item.title"
                :description="item.description"
            />
            <template #action>
                <li>
                    <Button size="small" type="primary" @click="handleView(item)">查看</Button>
                </li>
            </template>
        </ListItem>
    </List>
</template>
<script>
    const mockData = [
        {
            avatar: 'https://img1.doubanio.com/view/photo/s_ratio_poster/public/p2897210097.webp',
            title: '奥本海默 Oppenheimer',
            description: '随着战争阴云笼罩世界上空，各国紧锣密鼓抓紧军事竞赛。为了抢占先机，美国陆军中将莱斯利·格罗夫斯（马特·达蒙 Matt Damon 饰）找到量子力学与核物理学领域的扛鼎人物罗伯特·奥本海默（基里安·墨菲 Cillian Murphy 饰），力荐其担任曼哈顿计划的首席科学家以及洛斯阿拉莫斯国家实验室的总负责人。经过两年争分夺秒的研发，硕大的蘑菇云终于在荒原的上空腾起，也宣告着绞肉机一般的二战即将落下帷幕。',
            url: 'https://movie.douban.com/subject/35593344/?from=showing'
        },
        {
            avatar: 'https://img1.doubanio.com/view/photo/s_ratio_poster/public/p2896593530.webp',
            title: '威尼斯惊魂夜 A Haunting in Venice',
            description: '影片改编自阿加莎·克里斯蒂的小说《万圣节前夜的谋杀案》，故事发生在二战后的威尼斯，一个怪异的万圣节前夜，本已退休的著名侦探赫尔克里·波洛（肯尼斯·布拉纳 饰）将在世界上最迷人的城市威尼斯里过着安静自得的生活，他不情愿地被邀请前往一座破败阴森的宫殿参加聚会。当其中一位来宾被谋杀后，波洛被卷入了一个充满阴影和秘密的险恶世界。',
            url: 'https://movie.douban.com/subject/36117224/?from=showing'
        }
    ];

    export default {
        name: 'ins-list',
        emits: ['view'],
        props: {

        },
        data () {
            return {
                data: mockData
            }
        },
        methods: {
            handleView (item) {
                this.$emit('view', item.url);
            }
        }
    }
</script>