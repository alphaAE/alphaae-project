<template>
    <div class="projects-view">
        <div id="projects" class="background-alt-nth">
            <h2 class="heading">项目</h2>
            <div class="container-game">
                <project-game v-for="(data, i) in projectData" :data="data" :key="i"></project-game>
            </div>

        </div>


        <div id="projects" class="background-alt-nth">
            <h2 class="heading">3D Models</h2>
            <div class="container">

                <!-- One Project 3DModel Block -->
                <div class="project shadow-large">
                    <div class="project-glb">
                        <img class="image" src="assets/thumbs/model03-thumb.jpg" alt="assets/fulls/model03-full.glb" />
                    </div>
                </div>
                <!-- End of One Project 3DModel Block -->


                <div class="project shadow-large">
                    <div class="project-glb">
                        <img class="image" src="assets/thumbs/model04-thumb.jpg" alt="assets/fulls/model04-full.glb" />
                    </div>
                </div>

            </div>
        </div>

    </div>
</template>

<script>
import ProjectGame from '@/components/ProjectGame.vue'
import ProjectData from "@/data/projects.json"
export default {
    data() {
        return {
            projectData: ProjectData.projects,
            data: {
                id: 1,
                name: "Flappy bird demo",
                tag: ["Unity", "Unity", "Unity"],
                description: "描述描述描述描述描述描述描述描述描述描述描述描述描述描述描述描述描述描述描述描述描述描述描述描述描述描述描述描述描述描述描述描述描述描述",
                img: ["./assets/thumbs/project02-thumb.jpg"],
                createTime: "2020-01-01",
                repository: "https://www.thinkcmf.com/font/font_awesome/icon/steam-square",
                playUrl: ""
            }
        }
    },
    components: { ProjectGame },
}
</script>

<style>
#projects {
    padding-top: 75px;
}
</style>
