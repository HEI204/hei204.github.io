<script setup>
import SectionTitle from "./SectionTitle.vue";
import ProjectInfo from "../components/ProjectInfo.vue";

import { ref, onMounted, onUnmounted } from "vue";

import projects from "../data/projects.json"

const projectCarouselIdx = ref(0);

const handleIdxUpdate = (updateIdx) => {
    if (updateIdx === "prev")
        projectCarouselIdx.value--
    else
        projectCarouselIdx.value++
    if (projectCarouselIdx.value === projects.length)
        projectCarouselIdx.value = 0

    else if (projectCarouselIdx.value < 0)
        projectCarouselIdx.value = projects.length - 1
}

const handleDotClick = (event) => {
    projectCarouselIdx.value = parseInt(event.target.id.substring(4)) - 1
}

let interval;
onMounted(() => {
    interval = setInterval(() => handleIdxUpdate("next"), 5000)
})

onUnmounted(() => {
    clearInterval(interval);
})

</script>

<template>
    <section class="project-carousel-container pt-2 p-5">
        <SectionTitle title="Projects" />
        <div class="container mt-4">
            <div class="project-carousel">
                <div class="project-carousel-item">
                    <ProjectInfo class="my-3" :project="projects[projectCarouselIdx]" :showProjectDescription="false" />
                </div>
                <button @click="handleIdxUpdate('prev')"
                    class="project-carousel-btn bi bi-caret-left-fill prev"></button>
                <button @click="handleIdxUpdate('next')"
                    class="project-carousel-btn bi bi-caret-right-fill next"></button>
            </div>

            <ol class="dots mt-3 mb-2">
                <li v-for="project in projects" class="dot" key=":id"><span :id="`dot-${project.id}`"
                        :class="{ selected: projectCarouselIdx === project.id - 1 }" @click="handleDotClick"></span>
                </li>
            </ol>
        </div>
    </section>
</template>

<style>
.project-carousel-container {
    background-color: white;
}

.project-carousel {
    position: relative;
}

.project-carousel-item img {
    width: 100%;
    height: 100%;
}

.project-carousel-btn {
    border: none;
    background-color: rgba(54, 25, 25, 0);
    font-size: 20px;
    position: absolute;
    top: 0;
    width: 50px;
    height: 100%;
}

.project-carousel-btn:hover {
    background-color: rgba(243, 242, 242, 0.836);
    opacity: 0.1;
}

.prev {
    left: -50px;
}

.next {
    right: -50px;
}

.dots {
    cursor: pointer;
    display: flex;
    justify-content: center;
    list-style: none;
    margin: 0;
    padding: 0;
}

li span {
    display: inline-block;
    width: 1.5rem;
    height: 1.5rem;
    background-color: rgb(177, 177, 177);
    opacity: 0.5;
    background-clip: content-box;
    border: 0.25rem solid transparent;
    border-radius: 50%;
}

.selected {
    background-color: rgb(148, 148, 148);
    opacity: 1;
}
</style>
