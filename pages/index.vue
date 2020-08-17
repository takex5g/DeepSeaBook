<template>
  <div class="container">
    <Background class="background" :scrollY="scrollY" :size="size"></Background>
    <TopLayer class="toplayer" :scrollY="scrollY" :size="size"></TopLayer>
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

      <Chara name="mendako" style="grid-row: 10 / span 1; grid-column: 1 /span 1;">
        <template #name>メンダコ</template>
      </Chara>

      <!-- <CharaParallax
        name="mendako"
        :size="size"
        :scrollY="scrollY"
        :speed="1.5"
        style="grid-row:10 / span 1; grid-column: 2 /span 1;"
      >
        <template #name>メンダコ</template>
      </CharaParallax>-->

      <CharaDetail name="megamouse" position="center" style="grid-row: 27 / span 2;">
        <template #name>メガマウスザメ</template>
        <template #desc>巨大な口を持ち、迫力のある顔ですが実はプランクトンを食べているおとなしいサメです</template>
      </CharaDetail>

      <Chara name="mendako" style="grid-row: 32 / span 1; grid-column: 2 /span 1;">
        <template #name>オオナミカザリダマ</template>
      </Chara>
      <Chara name="mendako" style="grid-row: 34 / span 1; grid-column: 4 /span 1;">
        <template #name>テマリクラゲ</template>
      </Chara>
      <Chara name="mendako" style="grid-row: 36 / span 1; grid-column: 2 /span 1;">
        <template #name>ゲイコツナメクジウオ</template>
      </Chara>
      <Chara name="mendako" style="grid-row: 41 / span 1; grid-column: 2 /span 1;">
        <template #name>ゾウギンザメ</template>
      </Chara>
      <Chara name="mendako" style="grid-row: 45 / span 1; grid-column: 2 /span 1;">
        <template #name>ホオジロザメ</template>
      </Chara>

      <Chara name="mendako" style="grid-row: 49 / span 1; grid-column: 2 /span 1;">
        <template #name>コトクラゲ</template>
      </Chara>
      <Chara name="mendako" style="grid-row: 53 / span 1; grid-column: 2 /span 1;">
        <template #name>オウムガイ</template>
      </Chara>
      <Chara name="mendako" style="grid-row: 55/ span 1; grid-column: 2 /span 1;">
        <template #name>コウテイペンギン</template>
      </Chara>
      <Chara name="mendako" style="grid-row: 58 / span 1; grid-column: 2 /span 1;">
        <template #name>ギンザメ</template>
      </Chara>
      <Chara name="mendako" style="grid-row: 61 / span 1; grid-column: 2 /span 1;">
        <template #name>ミドリフサアンコウ</template>
      </Chara>

      <Chara name="mendako" style="grid-row: 64 / span 1; grid-column: 2 /span 1;">
        <template #name>ニシオンデンザメ</template>
      </Chara>
      <Chara name="mendako" style="grid-row: 67/ span 1; grid-column: 2 /span 1;">
        <template #name>ハダカカメガイ（クリオネ）</template>
      </Chara>
      <Chara name="mendako" style="grid-row: 68 / span 1; grid-column: 2 /span 1;">
        <template #name>ユウレイイイカ(600m)</template>
      </Chara>
      <Chara name="mendako" style="grid-row: 71/ span 1; grid-column: 2 /span 1;">
        <template #name>ワニトカゲギスの仲間</template>
      </Chara>
      <Chara name="mendako" style="grid-row: 74 / span 1; grid-column: 2 /span 1;">
        <template #name>キタカブトクラゲ</template>
      </Chara>
      <Chara name="mendako" style="grid-row: 77 / span 1; grid-column: 2 /span 1;">
        <template #name>カリフォルニアシラタマイカ</template>
      </Chara>
      <Chara name="mendako" style="grid-row: 80/ span 1; grid-column: 2 /span 1;">
        <template #name>スイショウウオ</template>
      </Chara>
      <Chara name="mendako" style="grid-row: 82 / span 1; grid-column: 2 /span 1;">
        <template #name>デメニギス</template>
      </Chara>

      <Chara name="mendako" style="grid-row: 85 / span 1; grid-column: 2 /span 1;">
        <template #name>ザラビクニン(800m指標)</template>
      </Chara>
      <!-- 1000m説明 -->
      <Chara name="mendako" style="grid-row: 90 / span 1; grid-column: 2 /span 1;">
        <template #name>オオグチボヤ</template>
      </Chara>
      <Chara name="mendako" style="grid-row: 90 / span 1; grid-column: 2 /span 1;">
        <template #name>オオグチボヤ</template>
      </Chara>
      <Chara name="mendako" style="grid-row: 93 / span 1; grid-column: 2 /span 1;">
        <template #name>クラゲダコ</template>
      </Chara>

      <CharaDetail name="daiouika" position="center" style="grid-row: 95 / span 2;">
        <template #name>ダイオウイカ</template>
        <template #desc>巨大な口を持ち、迫力のある顔ですが実はプランクトンを食べているおとなしいサメです</template>
      </CharaDetail>

      <Chara name="mendako" style="grid-row: 93 / span 1; grid-column: 2 /span 1;">
        <template #name>クラゲダコ</template>
      </Chara>
    </div>
  </div>
</template>

<script>
import Background from "@/components/Background";
import TopLayer from "@/components/TopLayer";
import CharaDetail from "@/components/CharaDetail";
import Chara from "@/components/Chara";
import CharaParallax from "@/components/CharaParallax";
export default {
  components: { Background, CharaDetail, Chara, CharaParallax, TopLayer },
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
      this.scrollY = window.pageYOffset;
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
.toplayer {
  position: fixed;
  left: 0px;
  top: 0px;
  /* width: 100%;
  height: 100%; */
  z-index: 2;
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
  grid-template-rows: repeat(200, 100px);
  grid-template-columns: repeat(4, 1fr);

  padding-left: 20px;
  padding-right: 20px;
}
h1 {
  grid-column: 1 / -1;
  margin: 0;
}
</style>
