<script setup>
import { RouterLink } from "vue-router";
</script>

<template>
  <div className="not-found-display d-flex justify-content-center mb-5">
    <div className="text-center">
      <h1 className="display-1 fw-bold">404</h1>
      <p className="fs-3">
        <span className="text-danger">Opps!</span> Page not found.
      </p>
      <p className="lead">The page you're looking for doesn't exist.</p>
      <RouterLink to="/" className="mt-3 btn btn-darkblue">
        Back to Homepage
      </RouterLink>
    </div>
  </div>
</template>
  
<style scoped>
.not-found-display {
  margin-top: 200px;
}
</style>
  