<script setup>
const { title, changeMarginClass } = defineProps(["title", "changeMarginClass"]);

const className = changeMarginClass ? "py-2" : "pt-5"
</script>

<template>
    <h1 :class="'display-6 fw-bold text-center ' + className">{{ title }}</h1>
</template>