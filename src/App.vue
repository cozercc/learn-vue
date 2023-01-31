<script setup>
import { RouterLink, RouterView } from "vue-router";
import { reactive, ref } from "vue";
import HelloWorld from "./components/HelloWorld.vue";

const test = ref(true);

function increment() {
  test.value = !test.value;
}

const myObject = reactive({
  title: "How to do lists in Vue",
  author: "Jane Doe",
  publishedAt: "2016-04-10",
});

const name = ref("Vue.js");

function greet(event) {
  alert(`hello ${name.value}`);
  if (event) {
    alert(event.target.tagName);
  }
}
</script>

<template>
  <header>
    <img
      alt="Vue logo"
      class="logo"
      src="@/assets/logo.svg"
      width="125"
      height="125"
    />

    <div class="wrapper">
      <HelloWorld msg="You did it!" />

      <nav>
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink>
      </nav>
      <div>
        <button @click="increment">{{ test }}</button>
        <button @click="greet">Greet</button>
      </div>
      <p v-if="test">YES</p>
      <p v-else>NO</p>
      <ul>
        <li v-for="(value, key, index) in myObject">
          {{ key }} : {{ value }} : {{ index }}
        </li>
      </ul>
    </div>
  </header>

  <RouterView />
</template>

<style scoped>
header {
  line-height: 1.5;
  max-height: 100vh;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  }
}
</style>
