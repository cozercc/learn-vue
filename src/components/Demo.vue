<script setup>
import { ref } from "vue";
import CustomInput from "./CustomInput.vue";

const myText = ref('');
const count = ref(0);
defineProps(['fontSize']);
defineEmits(['enlarge-text']);
</script>

<template>
    <CustomInput v-model.capitalize="myText" />
    <button @click="count++">{{ count }} times</button>
    <button @click="$emit('enlarge-text')">bigger size</button>
    <p>{{ fontSize }}</p>
</template>
<style></style>
