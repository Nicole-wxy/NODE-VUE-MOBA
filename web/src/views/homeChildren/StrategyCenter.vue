<template>
  <div>
    <swiperNav :categories="adsCats"></swiperNav>
  </div>
</template>
<script>
import swiperNav from "../../components/SwiperNav";
export default {
  name: "strategyCenter",
  created() {
    this.fetchAdsCats();
  },
  data() {
    return {
      adsCats: [],
    };
  },
  methods: {
    async fetchAdsCats() {
      const res = await this.$http.get("ads/list");
      this.adsCats = res.data[1].items;
    },
  },
  components: {
    swiperNav,
  },
};
</script>
