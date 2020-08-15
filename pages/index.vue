<template>
  <div class="container">
    <Background class="background" :scrollY="scrollY" :size="size"></Background>
    <div class="contents">
      <h1>魅惑の深海図鑑</h1>
      <!-- {{size.width}},{{size.height}} -->
      <CharaDetail name="mendako" position="left" style="grid-row: 2 / span 1;">
        <template #name>メンダコ</template>
        <template #desc>こんにちは深海魚ここは説明文</template>
      </CharaDetail>
      <CharaDetail name="mendako" position="right" style="grid-row: 4 / span 1;">
        <template #name>メンダコ</template>
        <template #desc>こんにちは深海魚うぇいうぇい</template>
      </CharaDetail>
      <CharaDetail name="mendako" position="center" style="grid-row: 6 / span 1;">
        <template #name>メンダコ</template>
        <template #desc>こんにちは深海魚うぇいうぇい</template>
      </CharaDetail>

      <Chara name="mendako" style="grid-row: 8 / span 1; grid-column: 1 /span 1;">
        <template #name>メンダコ</template>
      </Chara>
      <Chara name="mendako" style="grid-row: 9 / span 1; grid-column: 3 /span 1;">
        <template #name>メンダコ</template>
      </Chara>
      <Chara name="mendako" style="grid-row: 10 / span 1; grid-column: 5 /span 1;">
        <template #name>メンダコ</template>
      </Chara>
      <Chara name="mendako" style="grid-row: 11 / span 1; grid-column: -2 /span 1;">
        <template #name>メンダコ</template>
      </Chara>
    </div>
  </div>
</template>

<script>
import Background from "@/components/Background";
import CharaDetail from "@/components/CharaDetail";
import Chara from "@/components/Chara";
export default {
  components: { Background, CharaDetail, Chara },
  data: function () {
    return {
      scrollY: 0,
      size: {
        //ウィンドウサイズを格納
        width: 0,
        height: 0,
      },
    };
  },
  asyncData(context) {
    //jsonからデータを読みだし
    return {};
  },
  methods: {
    calculateScrollY() {
      this.scrollY = window.scrollY;
    },
    handleResize: function () {
      // resizeのたびにこいつが発火するので、ここでやりたいことをやる
      this.size.width = window.innerWidth;
      this.size.height = window.innerHeight;
    },
  },
  mounted() {
    window.addEventListener("scroll", _.throttle(this.calculateScrollY, 100)); //lodashでイベントを間引く
    window.addEventListener("resize", this.handleResize);
    this.handleResize();
  },
  beforeDestroy() {
    window.removeEventListener("scroll", this.calculateScrollY);
    window.removeEventListener("resize", this.handleResize);
  },
  computed: {},
  watch: {},
  filters: {},
};
</script>

<style scoped>
.background {
  position: fixed;
  left: 0px;
  top: 0px;
  width: 100%;
  height: 100%;
  z-index: -1;
}
.container {
}
@media (min-width: 680px) {
  .contents {
    width: 500px;
    margin: 0 auto;
  }
}
.contents {
  z-index: 2;
  background-color: rgba(0, 0, 0, 0.055);
  text-align: center;
  display: grid;
  grid-template-rows: repeat(100, 100px);
  grid-template-columns: repeat(6, 1fr);

  padding-left: 20px;
  padding-right: 20px;
}
h1 {
  grid-column: 1 / -1;
  margin: 0;
}
</style>
