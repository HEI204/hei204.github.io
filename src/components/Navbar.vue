<script setup>
import { RouterLink } from "vue-router";

const navLinks = [
  {
    linkTo: "/",
    icon: "bi bi-house",
    text: "Home",
  },
  {
    linkTo: "/about",
    icon: "bi bi-person",
    text: "About",
  },
  {
    linkTo: "/project",
    icon: "bi bi-person",
    text: "Projects",
  },
]
</script>

<template>
  <header class="fixed-top">
    <nav class="navbar navbar-expand-md navbar-light py-2 p-4 p-md-3 border-bottom border-1">
      <div class="container">
        <RouterLink class="navbar-brand" to="/">
          <img src="../assets/images/logo.png" alt="logo" width="32" height="32" class="d-inline-block align-text-top">
        </RouterLink>
        <button class="navbar-toggler collapsed position-relative shadow-none border-0" type="button"
          data-bs-toggle="collapse" data-bs-target="#responsive-navbar" aria-controls="responsive-navbar"
          aria-expanded="false" aria-label="Toggle navigation">
          <span> </span>
          <span> </span>
          <span> </span>
        </button>
        <div class="collapse navbar-collapse" id="responsive-navbar">
          <ul class="ms-auto navbar-nav mb-2 mb-lg-0 ">
            <li v-for="link in navLinks" class="ps-3 nav-item" :key="link.text">
              <RouterLink :to="link.linkTo" class="nav-link">
                <i :class="link.icon"></i>
                {{ link.text }}
              </RouterLink>
            </li>
          </ul>
        </div>
      </div>
    </nav>
  </header>
</template>

<style scoped>
.navbar-toggler:focus,
.navbar-toggler:active {
  outline: 0;
}

.navbar-toggler span {
  display: block;
  background-color: var(--darkblue-color);
  height: 3px;
  width: 25px;
  margin-top: 4px;
  margin-bottom: 4px;
  -webkit-transform: rotate(0deg);
  -moz-transform: rotate(0deg);
  -o-transform: rotate(0deg);
  transform: rotate(0deg);
  position: relative;
  left: 0;
  opacity: 1;
}

.navbar-toggler span:nth-child(1),
.navbar-toggler span:nth-child(3) {
  -webkit-transition: transform .35s ease-in-out;
  -moz-transition: transform .35s ease-in-out;
  -o-transition: transform .35s ease-in-out;
  transition: transform .35s ease-in-out;
}

.navbar-toggler:not(.collapsed) span:nth-child(1) {
  position: absolute;
  left: 12px;
  top: 10px;
  -webkit-transform: rotate(135deg);
  -moz-transform: rotate(135deg);
  -o-transform: rotate(135deg);
  transform: rotate(135deg);
  opacity: 0.9;
}

.navbar-toggler:not(.collapsed) span:nth-child(2) {
  height: 12px;
  visibility: hidden;
  background-color: transparent;
}

.navbar-toggler:not(.collapsed) span:nth-child(3) {
  position: absolute;
  left: 12px;
  top: 10px;
  -webkit-transform: rotate(-135deg);
  -moz-transform: rotate(-135deg);
  -o-transform: rotate(-135deg);
  transform: rotate(-135deg);
  opacity: 0.9;
}

.nav-item {
  font-size: 18px;
}

.nav-link:hover,
.router-link-active {
  color: var(--darkblue-color) !important
}

.show .navbar-nav,
.collapsing .navbar-nav {
  margin-top: 8px;
}

.show .navbar-nav .nav-item,
.collapsing .navbar-nav .nav-item {
  text-align: center;
}

.bi {
  margin-right: 3px;
}
</style>
