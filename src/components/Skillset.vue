<script setup>
import SectionTitle from "./SectionTitle.vue";

const skillset = [
    {
        imgSrc: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original-wordmark.svg",
        alt: "python",
    },
    {
        imgSrc: "https://upload.wikimedia.org/wikipedia/commons/1/18/ISO_C%2B%2B_Logo.svg",
        alt: "c++",
    },
    {
        imgSrc: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/java/java-original-wordmark.svg",
        alt: "java",
    },
    {
        imgSrc: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg",
        alt: "javascript",
    },
    {
        imgSrc: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original-wordmark.svg",
        alt: "html5",
    },
    {
        imgSrc: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original-wordmark.svg",
        alt: "css3",
    },
]

const selfLearningSkillset = [
    {
        imgSrc: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/kubernetes/kubernetes-original-wordmark.svg",
        alt: "kubernetes",
    },
    {
        imgSrc: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/terraform/terraform-original-wordmark.svg",
        alt: "terraform",
    },
    {
        imgSrc: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/jenkins/jenkins-original.svg",
        alt: "jenkins",
    },
    {
        imgSrc: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original-wordmark.svg",
        alt: "python",
    },
    {
        imgSrc: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg",
        alt: "javascript",
    },
    {
        imgSrc: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/vuejs/vuejs-original-wordmark.svg",
        alt: "vuejs",
    },
    {
        imgSrc: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/react/react-original-wordmark.svg",
        alt: "react",
    },
    {
        imgSrc: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/flask/flask-original-wordmark.svg",
        alt: "flask",
    },
    {
        imgSrc: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/django/django-plain.svg",
        alt: "django",
    },
    {
        imgSrc: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/bootstrap/bootstrap-original.svg",
        alt: "bootstrap5",
    },
]
</script>

<template>
    <div class="skillset px-5 text-center">
        <SectionTitle title="Skillsets" />
        <div class="mt-5">
            <h2 class="skillset-subtitle mb-4">Learn from university:</h2>
            <div class="d-flex justify-content-center flex-wrap">
                <img v-for="skill in skillset" class="skill-icon mx-2 mb-4" :src="skill.imgSrc" :alt="skill.alt" />
            </div>
        </div>

        <div>
            <h2 class="skillset-subtitle mb-4">Self learning:</h2>
            <div class="d-flex justify-content-center flex-wrap">
                <img v-for="skill in selfLearningSkillset" class="skill-icon mx-2 mb-4" :src="skill.imgSrc"
                    :alt="skill.alt" />
            </div>
        </div>
    </div>
</template>

<style scoped>
.skill-icon {
    width: 55px;
    height: 55px;
}


.skillset-subtitle {
    font-size: 16px;
    font-weight: bold;
}
</style>
