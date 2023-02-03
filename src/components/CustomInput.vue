<script setup>
defineProps({
    firstName: String,
    lastName: String,
});
defineEmits(["update:firstName", "update:lastName"]);
</script>

<template>
    <input
        :value="firstName"
        @input="$emit('update:firstName', $event.target.value)"
    />
    <input
        :value="lastName"
        @input="$emit('update:lastName', $event.target.value)"
    />
</template>
<style></style>
