<script setup>
import { ref } from "vue";
import CustomInput from "./CustomInput.vue";

const myText = ref('');
const count = ref(0);
defineProps(['fontSize']);
</script>

<template>
    <CustomInput v-model.capitalize="myText" />
    <button @click="count++">{{ count }} times</button>
    <p>{{ fontSize }}</p>
</template>
<style></style>
