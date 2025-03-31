<template>
 this page id is :  {{ id }}
</template>

<script setup>
const routes = useRoute()
const id = routes.params.id
</script>
<style>

</style>