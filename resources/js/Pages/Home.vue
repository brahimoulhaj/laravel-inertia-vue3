<template>
    <Head title="Home Page"/>
    <h2>Home Page</h2>
    <p>welcome, {{ name }}</p>
</template>

<script setup>
import { Head } from "@inertiajs/inertia-vue3";
defineProps({
    name: {
        type: String,
    },
});
</script>

<style></style>
