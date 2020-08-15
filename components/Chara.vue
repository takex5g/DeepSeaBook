<template>
  <div class="chara">
    <img :src="require('@/assets/img/chara/'+name+'.png')" />
    <h3>
      <slot name="name">名前が設定されていません</slot>
    </h3>
  </div>
</template>

<script>
import anime from "animejs"; // animejsの読み込み
export default {
  props: {
    name: {
      type: String,
    },
  },
  data: function () {
    return {};
  },
  mounted() {},
  methods: {},
  computed: {},
  watch: {},
  filters: {},
};
</script>

<style scoped>
.chara {
  max-width: 100%;
  max-height: 100%;
  display: grid;
}
.chara img {
  height: auto;
  width: 100%;
}
.chara h3 {
  /*回り込み説明文付き */
  text-align: center;
  white-space: nowrap;
}
</style>
