<script setup>
import SectionTitle from "./SectionTitle.vue";
import { ref, computed, Transition } from "vue"
import { useMediaQuery } from '@vueuse/core'

const isLargeScreen = useMediaQuery('(min-width: 1000px)')
const showMore = ref(false)
const btnText = computed(() =>
    showMore.value ? "Show Less..." : "Show More..."
);
</script>

<template>
    <div class="self-intro px-sm-2 px-md-5 pb-5 d-flex flex-column align-items-center">
        <SectionTitle title="About me" />
        <p class="mt-5">
            I am a third-year computer science student at City University of Hong Kong with a strong interest in web
            development. Through my coursework and personal projects, I have gained some experiences in various tech
            stacks
            including React, and Django.
        </p>

        <Transition>
            <div v-if="showMore || isLargeScreen">
                <p>
                    In addition to my technical skills, I am a team player with a proven track
                    record of collaborating effectively with others. Whether working on group projects or contributing
                    to a
                    team
                    effort, I am known for my ability to communicate clearly and effectively, as well as my willingness
                    to
                    listen to others' ideas and contribute my own. I am a proactive and patient problem-solver who is
                    always
                    eager to take
                    on new challenges and find creative solutions to difficult problems.
                </p>
                <p>
                    Outside of my studies, I enjoy reading a wide variety of books including fiction, sci-fi, romance,
                    and
                    even
                    philosophy and psychology.
                </p>
            </div>
        </Transition>

        <button v-if="!isLargeScreen" @click="showMore = !showMore" class="btn btn-darkblue mt-4">
            {{ btnText }}
        </button>
    </div>
</template>

<style scoped>
.v-enter-active,
.v-leave-active {
    transition: opacity 0.3s ease;
}

.v-enter-from,
.v-leave-to {
    opacity: 0;
}
</style>