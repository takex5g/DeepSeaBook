<template>
  <div class="chara" :class="position">
    <img :src="require('@/assets/img/chara/'+name+'.png')" />
    <div>
      <h3>
        <slot name="name">名前が設定されていません</slot>
      </h3>
      <p>
        <slot name="desc">説明文が設定されていません</slot>
      </p>
    </div>
  </div>
</template>

<script>
import anime from "animejs"; // animejsの読み込み
export default {
  props: {
    position: {
      type: String,
    },
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
  grid-column: 1 / -1;
}
.chara h3 {
  margin: 0;
  white-space: nowrap;
}
.chara img {
  height: 100%;
  width: auto;
}
.chara div {
  /*回り込み説明文付き */
  text-align: left;
}

/**全体ボックスの設定 */
.left {
  /*回り込み説明文付き */
  grid-template-columns: auto 1fr;
}
.center {
  /* grid-template-columns: 1fr auto; */
}
.right {
  grid-template-columns: 1fr auto;
}
/*ここまで*/

/*名前説明の設定*/
.left div {
  margin-left: 10px;
  text-align: left;
}
.right div {
  margin-right: 10px;
  text-align: right;
}
.center div {
  text-align: center;
}
/**ここまで */

/*画像の設定*/
.right img {
  order: 2; /*順番を入れかえ */
}
.left img {
}
.center img {
  margin: auto;
}
/**ここまで */
</style>
