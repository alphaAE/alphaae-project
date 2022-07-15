<template>
    <div>
        <el-carousel :autoplay="false" type="card" :loop="false" trigger="click" height="300px">
            <el-carousel-item v-if="data.videoUrl" :key="-1">
                <iframe width="100%" height="100%" :src="data.videoUrl" scrolling="no" border="0" frameborder="no"
                    framespacing="0" allowfullscreen="true"> </iframe>
            </el-carousel-item>
            <el-carousel-item v-for="(item, i) in data.img" :key="i">
                <img :src="item" width="100%" />
            </el-carousel-item>
        </el-carousel>

        <div class="project-info">
            <el-row>
                <el-col :span="18">
                    <h1> {{ data.name }}</h1>
                    <p class="project-tags">
                        <span v-for="(item, i) in data.tag" :key="i"
                            :style="'background-color: ' + color.tags[item] + ';'">{{ item }}</span>
                    </p>

                    <p style="font-size: 1.1em;">
                        {{ data.description }}
                    </p>
                </el-col>
                <el-col :span="6">
                    <div style="position:absolute;  bottom:0; right:0;">
                        <p style="margin: 15px 0 0 0;" v-if="data.repository">
                            <a :href="data.repository" target="_blank">
                                <el-button type="primary">
                                    <i class="fa fa-github-alt fa-fw fa-lg" aria-hidden="true"
                                        style="margin-right: 10px;"></i>
                                    仓库地址
                                </el-button>
                            </a>
                        </p>
                        <p style="margin: 15px 0 0 0;" v-if="data.playUrl">
                            <a :href="data.playUrl" target="_blank">
                                <el-button type="warning">
                                    <i class="fa fa-gamepad fa-fw fa-lg" aria-hidden="true"
                                        style="margin-right: 10px;"></i>
                                    在线演示
                                </el-button>
                            </a>
                        </p>
                    </div>
                </el-col>
            </el-row>
        </div>
    </div>
</template>

<script>
import colorJson from '@/data/color.json'
export default {
    props: {
        data: Object
    },
    data() {
        return {
            color: colorJson,
        }
    }
}
</script>

<style scoped>
.project-tags>span {
    margin: 0 4px;
    padding: 4px;
    color: white;
    font-size: 1.2em;
    background: rgb(131, 131, 131);
    border-radius: 4px;
}
</style>