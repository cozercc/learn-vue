<script setup>
import { ref } from "vue";
import CustomInput from "./CustomInput.vue";

const myText = ref('');
</script>

<template>
    <CustomInput v-model.capitalize="myText" />
</template>
<style></style>
