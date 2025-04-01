<template>
  <div class="error-container">
    <h1 v-if="error.statusCode === 404">404 - Page Not Found 😢</h1>
    <h1 v-else>Oops! Something went wrong 😬</h1>
    <p>{{ error.statusMessage || "An unexpected error occurred." }}</p>
    <NuxtLink to="/">Go Back Home</NuxtLink>
  </div>
</template>

<script setup>
defineProps(["error"]);
defineErrorLayout(); // Ensures Nuxt recognizes this as the error layout
</script>

<style scoped>
.error-container {
  text-align: center;
  padding: 50px;
}
</style>
