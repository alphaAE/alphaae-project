<template>
    <div class="project-game shadow-large" style="height: 225px;">
        <div class="project-image" style="height: 225px; width: 400px;">
            <el-carousel height="225px" v-if="data.img.length > 1">
                <el-carousel-item v-for="(item, i) in data.img" :key="i">
                    <img :src="item" />
                </el-carousel-item>
            </el-carousel>
            <img v-else :src="data.img[0]" />
        </div>
        <div class="project-info">
            <h3 style="margin: 0 0 12px 0;"> {{ data.name }}</h3>
            <p class="project-tags">
                <span v-for="(item, i) in data.tag" :key="i">
                    {{ item }}
                </span>
            </p>

            <p>
                {{ data.description }}
            </p>
            <p class="project-link">
                <span v-if="data.repository">
                    <i class="fa fa-github-alt fa-fw" aria-hidden="true" style="margin-right: 10px;"></i>
                    <a :href="data.repository" target="_blank">仓库地址</a>
                </span>

                <span v-if="data.playUrl">
                    <i class="fa fa-gamepad fa-fw" aria-hidden="true" style="margin-right: 10px;"></i>
                    <a :href="data.playUrl" target="_blank">在线演示</a>
                </span>

                <span v-if="data.videoUrl">
                    <i class="fa fa-youtube-play fa-fw" aria-hidden="true" style="margin-right: 10px;"></i>
                    <a :href="data.videoUrl" target="_blank">在线观看</a>
                </span>
            </p>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        data: {
            id: Intl,
            name: String,
            tag: Array,
            description: String,
            img: Array,
            createTime: String,
            repository: String,
            playUrl: String
        }
    }
}
</script>

<style>
.project-tags {}

.project-tags>span {
    margin: 0 4px;
    padding: 4px;
    color: white;
    font-size: 0.4em;
    background: rgb(131, 131, 131);
    border-radius: 4px;
}

.project-link>span {
    margin: 0 10px;
}
</style>