<template>
    <div class="project shadow-large">
        <div class="look-detail"></div>
        <div class="project-image" style="height: 168px; width: 300px;">
            <img height="168px" :src="data.img[0]" />
        </div>
        <div class="project-info">
            <h3 style="margin: 0 0 12px 0;"> {{ data.name }}</h3>
            <p class="project-tags">
                <span v-for="(item, i) in data.tag" :key="i" :style="'background-color: ' + color.tags[item] + ';'">{{
                        item
                }}</span>
            </p>

            <p>
                {{ data.descriptionMini }}
            </p>
        </div>
    </div>

</template>

<script>
import colorJson from '@/data/color.json'
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
    },
    data() {
        return {
            color: colorJson,
        }
    }
}
</script>

<style scoped>
img {
    width: 100%;
}

.project-tags>span {
    margin: 0 4px;
    padding: 4px;
    color: white;
    font-size: 0.4em;
    background: rgb(131, 131, 131);
    border-radius: 4px;
}

.project {
    transition-duration: 0.2s;
    cursor: pointer;
}

.project:hover {
    color: #3498db;
    transform: scale(1.1);
    box-shadow: 0 3px 15px rgba(0, 0, 0, 0.02), 0 3px 15px rgba(0, 0, 0, 0.07);
}
</style>