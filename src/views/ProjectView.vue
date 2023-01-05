<script setup>
import SectionTitle from "../components/SectionTitle.vue";
import ProjectInfo from "../components/ProjectInfo.vue";
import projects from "../data/projects.json"

let reversedProjects = []

projects.forEach((project) => {
    reversedProjects.unshift(project);
});

</script>

<template>
    <section class="project-section">
        <SectionTitle title="Projects" :changeMarginClass="true" />
        <div v-for="project in reversedProjects" class="project-container p-5 my-5" :key="project.id">
            <div class="container">
                <ProjectInfo :project="project" :showProjectDescription="true" />
            </div>
        </div>
    </section>
</template>

<style scoped>
.project-container {
    background-color: white;
}
</style>


