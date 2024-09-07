<script setup>
import SectionTitle from "./SectionTitle.vue";
</script>

<template>
    <section class="intro p-5 pt-5">
        <SectionTitle title="Hi, I'm Ray Ng" />
        <ul class="icons">
            <li><a class="bi bi-github" href="https://github.com/HEI204" target="_blank"></a>
            </li>
            <li><a class="ps-3 bi bi-linkedin" href="https://www.linkedin.com/in/ray-ng-5a7b91214" target="_blank"></a>
            </li>
        </ul>
        <a href="/file/Resume.pdf" download className="mt-4 btn btn-darkblue">
            Download Resume <i class="bi bi-file-earmark-arrow-down-fill"></i>
        </a>
    </section>
</template>

<style scoped>
.intro {
    margin-top: 60px;
    background-color: #f7f7f9;
    text-align: center;
}

.icons {
    margin-bottom: 0;
    padding-left: 0;
    display: flex;
    font-size: 22px;
    justify-content: center;
    align-items: center;
    list-style: none;
}

.icons li a {
    color: var(--darkblue-color);
}

.icons li a:hover {
    color: var(--darkblue-hover-color);
}
</style>
