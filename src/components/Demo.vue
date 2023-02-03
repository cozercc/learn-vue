<script setup>
import { ref } from "vue";
import CustomInput from "./CustomInput.vue";

const first = ref("John");
const last = ref("Doe");
</script>

<template>
    <h1>{{ first }} {{ last }}</h1>
    <CustomInput v-model:first-name="first" v-model:last-name="last" />
</template>
<style></style>
