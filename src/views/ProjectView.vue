<template>
    <div class="projects-view">
        <div id="projects" class="background-alt-nth">
            <h2 class="heading">精选</h2>
            <div class="container-game">
                <project-game-star v-for="(data, i) in starData" :data="data" :key="i"></project-game-star>
            </div>

        </div>

        <div id="projects" class="background-alt-nth">
            <h2 class="heading">Other</h2>
            <div class="container">
                <project-game v-for="(data, i) in otherData" :data="data" :key="i" @click.native="openDialog(data)">
                </project-game>
            </div>
        </div>

        <el-dialog :visible.sync="dialogVisible" @closed="closeDialog">
            <project-info-dialog :data="selectProject"></project-info-dialog>
        </el-dialog>

    </div>
</template>

<script>
import ProjectGameStar from '@/components/ProjectGameStar.vue'
import ProjectGame from '@/components/ProjectGame.vue'
import ProjectData from "@/data/projects.json"
import ProjectInfoDialog from '@/components/ProjectInfoDialog.vue'
export default {
    components: { ProjectGameStar, ProjectGame, ProjectInfoDialog },
    data() {
        return {
            dialogVisible: false,
            selectProject: {},
            projectData: ProjectData.projects,
            starData: [],
            otherData: []
        }
    },
    created() {
        this.projectData.forEach((item) => {
            if (item.isStar) {
                this.starData.push(item);
            } else {
                this.otherData.push(item);
            }

        })
    },
    methods: {
        openDialog(data) {
            this.selectProject = data;
            this.dialogVisible = true;
        },
        closeDialog() {
            this.selectProject = {};
        }
    }
}
</script>

<style>
#projects {
    padding-top: 75px;
}
</style>
