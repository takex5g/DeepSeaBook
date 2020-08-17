<template>
  <div class="chara" :style="parallax">
    <img :src="require('@/assets/img/chara/'+name+'.png')" />
    <h3>
      <slot name="name">名前が設定されていません</slot>
    </h3>
  </div>
</template>

<script>
export default {
  props: {
    name: {
      type: String,
    },
    size: {
      type: Object,
    },
    scrollY: {
      type: Number,
    },
    speed: {
      type: Number,
    },
  },
  data: function () {
    return {
      rect: {
        type: Object,
      },
      offset: 0,
      data: 0,
    };
  },
  mounted() {
    this.offset = this.$el.getBoundingClientRect().top + window.pageYOffset;
  },
  methods: {},
  computed: {
    parallax() {
      /*      console.log(
        "0<",
        this.rect.bottom,
        "  ",
        this.rect.top,
        "<",
        this.size.height,
        "  offset",
        this.offset
      );*/
      // console.log(this.rect);
      console.log(
        "ok",
        this.data,
        -(this.size.height / (this.speed - 1) / 2 + this.rect.height) + "px",
        this.size.height
      );
      if (0 < this.rect.bottom == false) {
        this.data =
          (this.scrollY + this.size.height - this.offset) * (this.speed - 1);
        return { top: -this.data + "px" };
        return {
          top: -(this.size.height * this.speed + this.rect.height) + "px",
        };
      } else if (this.rect.top < this.size.height == false) {
        return { top: "0px" };
      } else {
        this.data =
          (this.scrollY + this.size.height - this.offset) * (this.speed - 1);
        return { top: -this.data + "px" };
      }
    },
  },
  watch: {
    scrollY() {
      this.rect = this.$el.getBoundingClientRect();
    },
  },
};
</script>

<style scoped>
.chara {
  max-width: 100%;
  max-height: 100%;
  display: grid;
  position: relative;
  transition-duration: 0.3s;
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
