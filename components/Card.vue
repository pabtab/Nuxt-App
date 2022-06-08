<template>
  <div>
    <!-- <p v-if="$fetchState.pending">
      <span class="loading"></span>
    </p> -->
    <!-- <p v-else-if="$fetchState.error">Error while fetching mountains 🤬</p> -->
    <ul>
      <li
        v-for="river in rivers"
        :key="river.title"
        class="border border-1 rounded-lg p-4 shadow-md shadow-cyan-500/50"
      >
        <NuxtLink :to="{ name: 'river', params: { slug: river.slug, river } }">
          {{ river.title }}
        </NuxtLink>
        <hr class="my-4" />
        <img :src="river.image" />
        <p>{{ river.description }}</p>
      </li>
    </ul>
    <!-- <button @click="$fetch">Refresh Data</button> -->
  </div>
</template>

<script>
export default {
  props: ["rivers"],
  // async fetch() {
  //   const res = await fetch("https://api.nuxtjs.dev/rivers");
  //   const data = await res.json();
  //   this.rivers = data;
  // },
};
</script>

<style>
li {
  margin-bottom: 0.5rem;
}
li:first-letter {
  text-transform: uppercase;
}
.loading {
  display: inline-block;
  width: 1.5rem;
  height: 1.5rem;
  border: 4px solid rgba(9, 133, 81, 0.705);
  border-radius: 50%;
  border-top-color: #158876;
  animation: spin 1s ease-in-out infinite;
}
@keyframes spin {
  to {
    -webkit-transform: rotate(360deg);
  }
}
</style>
