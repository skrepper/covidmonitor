<template>
  <main class="flex flex-col align-center justify-center text-center">
    <div class="text-gray-500 mb-6 mt-10 text-3xl">Fetching Data</div>
    <img :src="loadingImage" class="w-24 m-auto" alt="hourglass" />
  </main>
</template>

<script>

export default {
  name: 'Home',
  components: {
  },
  data() {
    return {
      loading: true,
      title: "Global",
      loadingImage: require("../assets/loading.gif"),
    };
  },
}
</script>
