<template>
  <main v-if="!loading">
    <DataTitle :dataDate="dataDate" :text="title" />
  </main>
  <main class="flex flex-col align-center justify-center text-center" v-else>
    <div class="text-gray-500 mb-6 mt-10 text-3xl">Fetching Data</div>
    <img :src="loadingImage" class="w-14 m-auto" alt="hourglass" />
  </main>
</template>

<script>
  export default {
    name: 'Home',
    components: {},
    data() {
      return {
        loading: true,
        title: "Global",
        dataDate: "",
        loadingImage: require("../assets/loading.gif"),
      };
    },
    methods: {
      async fetchCovidData() {
        const res = await fetch("https://api.covid19api.com/summary");
        const data = res.json();
        return data;
      },
    },
    async created() {
      const data = await this.fetchCovidData();
      this.dataDate = data.Date;
    },
  }
</script>