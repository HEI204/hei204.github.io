<script setup>
const { project } = defineProps(["project", "showProjectDescription"])


</script>

<template>
    <div class="project-info">
        <div class="mb-3 text-muted d-flex justify-content-center align-items-center">
            <h5 class="project-title">{{ project.title }} </h5>
            <a class="ms-3 bi bi-github project-link" :href="project.href" target="_blank"></a>
            <a class="ms-2 bi bi-globe2 project-link" :href="project.website" target="_blank"></a>
        </div>
        <p class="tech-stack"> Skill invovled: {{ project.techStack }}</p>
        <img class="img-fluid" :src="project.imgSrc" :alt="project.title" />
        <p v-if="showProjectDescription" class="project-description mt-4">{{ project.description }}</p>
    </div>
</template>

<style scoped>
.project-info {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

.project-title {
    font-size: 18px;
    font-weight: bold;
    margin-bottom: 0;
}

.tech-stack,
.project-description {
    font-size: 16px;
    color: #6c757d;
}

@media screen and (max-width: 736px) {

    .tech-stack,
    .project-description {
        font-size: 14px;
    }
}

.project-link {
    color: var(--darkblue-color);
    font-size: 18px;
}
</style>
