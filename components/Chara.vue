<template>
  <div class="chara">
    <img :src="require('@/assets/img/chara/mendako.png')" />

    <h3>
      <slot name="name">名前が設定されていません</slot>
    </h3>
    <p>
      <slot>説明文が設定されていません</slot>
    </p>
  </div>
</template>

<script>
import anime from "animejs"; // animejsの読み込み
export default {
  props: {},
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
</style>
