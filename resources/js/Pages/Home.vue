<template>
    <h2>Home Page</h2>
    <p>welcome, {{ name }}</p>
</template>

<script setup>
defineProps({
    name: {
        type: String,
    },
});
</script>

<style></style>
