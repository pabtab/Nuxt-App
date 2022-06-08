<template>
  <main class="p-5">
    <h1>Home Page</h1>
    <NuxtLink to="/about" class="underline">About page</NuxtLink>
    <button @click="showAlert">Click me</button>
    <LazyAlert v-if="show" />

    <hr />

    <Card :rivers="rivers" />
  </main>
</template>

<script>
export default {
  name: "IndexPage",
  data() {
    return {
      show: false,
      rivers: [],
    };
  },
  methods: {
    showAlert() {
      this.show = true;
    },
  },
  async asyncData({ $axios }) {
    const rivers = await $axios.$get("https://api.nuxtjs.dev/rivers");
    console.log(rivers);
    return { rivers };
  },
};
</script>
