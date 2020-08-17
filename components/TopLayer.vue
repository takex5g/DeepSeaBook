<template>
  <div class="container">{{suisin}}m</div>
</template>

<script>
import anime from "animejs"; // animejsの読み込み
export default {
  components: {
    anime,
  },
  props: {
    scrollY: {
      type: Number,
    },
    size: {
      type: Object,
    },
  },
  data: function () {
    return {};
  },
  mounted() {},
  methods: {},
  computed: {
    suisin() {
      let tmp = Math.floor(this.scrollY / 10);
      let tmp2 = Math.floor((tmp - 800) * 4) + 800;
      let tmp3 = Math.floor((tmp2 - 1000) / 3) + 1000;
      if (tmp <= 800) {
        return tmp;
      } else if (tmp2 < 1000) {
        return tmp2;
      } else if (tmp3 < 2000) {
        return tmp3;
      }
    },
  },
  filters: {},
};
</script>

<style scoped>
.container {
  text-align: center;
  font-size: 100px;
}
</style>
