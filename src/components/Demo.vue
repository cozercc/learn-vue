<script setup>
import { ref } from "vue";

const message = ref("Hello World");

function reverseMessage() {
    message.value = message.value.split("").reverse().join("");
}

function notify() {
    alert("WTF");
}
</script>

<template>
    <h1>{{ message }}</h1>

    <button @click="reverseMessage">Reverse Message</button>

    <button v-on:click="notify">alert</button>

    <button @click="message += 666">@click="message += 666"</button>

    <button @click="message = 'First'">Clear All</button>

    <a href="https://vuejs.org" @click.prevent="notify">
        A link with e.preventDefault()
    </a>
</template>
<style>

</style>
