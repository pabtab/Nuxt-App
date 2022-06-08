<template>
  <div class="flex flex-col items-center p-5">
    <h1 class="text-lg font-mono">{{ river.title }}</h1>
    <img class="my-5" :src="river.image" :alt="river.title" />
    <p>
      {{ river.description }}
    </p>
  </div>
</template>

<script>
export default {
  async asyncData({ params }) {
    return {
      river: params.river,
    };
  },
};
</script>

<style></style>
