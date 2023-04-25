<template>
    <footer>&copy; José Ortega -- {{ currentYear }}</footer>
</template>

<script setup>
    const currentYear = new Date().getUTCFullYear()


</script>