<template>
  <div class="container">
    <Background class="background" :scrollY="scrollY" :size="size"></Background>
    <div class="contents">
      <h1>魅惑の深海図鑑</h1>
      {{size.width}},{{size.height}}
      <Chara name="mendako" position="center">
        <template #name>メンダコ</template>
        こんにちは深海魚
      </Chara>

      <!-- <br v-for="i in 500" :key="i" /> -->
    </div>
  </div>
</template>

<script>
import Background from "@/components/Background";
import Chara from "@/components/Chara";
export default {
  components: { Background, Chara },
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
  grid-template-rows: repeat(100, 1fr);
  grid-template-columns: auto auto auto auto;
}
h1 {
  grid-column: 1 / 5;
  margin: 0;
}
</style>
