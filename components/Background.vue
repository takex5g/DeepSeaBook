<template>
  <div class="bg_container">
    <div class="bubblebox">
      <div class="bubble" :style="bubble_style[item-1]" v-for="item in 50" :key="item"></div>
    </div>
    <!-- <div class="tes green"></div>
    <div class="tes red"></div>
    <div class="tes blue"></div>-->
  </div>
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
    return {
      bubble_animation: {
        type: Object,
      },
      bubble_pos: [],
      bubble_style: [],
    };
  },
  mounted() {
    /*
    anime({
      targets: ".bg_container .tes",
      translateX: "13.5rem",
      scale: [0.75, 0.9],
      delay: function (el, i) {
        return i * 80;
      },
      direction: "alternate",
      loop: true,
    });*/

    for (let i = 0; i < 50; i++) {
      this.bubble_pos.push({
        pos: 0,
        ofset: 0,
        rand: 0,
      });
      this.bubble_pos[i].pos = this.size.height;
      this.bubble_pos[i].rand = Math.random();
      this.bubble_style.push({
        width: "0",
        height: "0",
        transform: "0",
        "transition-duration": "0.0s",
      });
    }
  },
  methods: {
    bubble_size() {
      //泡のサイズ決定
      for (let j = 0; j < this.bubble_pos.length; j++) {
        if (this.bubble_pos[j] != undefined) {
          let rand = Math.floor(this.bubble_pos[j].rand * 100) / 100;
          this.bubble_style[j].width = rand * 10 + "px";
          this.bubble_style[j].height = rand * 10 + "px";
          this.bubble_style[j].transform =
            "translateY(" + this.bubble_pos[j].pos + "px)";
        }
      }
    },
  },
  computed: {},
  watch: {
    scrollY() {
      let self = this;
      for (let i = 0; i < this.bubble_pos.length; i++) {
        let scroll_val = (this.scrollY / 2) * this.bubble_pos[i].rand;
        if (this.bubble_pos[i].pos < -this.size.height - 50) {
          //最上部に来たら最下部に戻る
          this.bubble_pos[i].ofset = scroll_val; //
        } else if (this.bubble_pos[i].pos > 10) {
          //最下部に来たら最上部に戻る
          this.bubble_pos[i].ofset -= this.size.height + 50;
        }
        this.bubble_pos[i].pos = -scroll_val + this.bubble_pos[i].ofset;
      }
      // this.bubble_animation = anime({
      //   targets: ".bubble",
      //   translateY: function (el, i) {
      //     return self.bubble_pos[i].pos;
      //   },
      //   duration: 100,
      //   easing: "linear", //easeInOutSine
      // });
      this.bubble_size();
    },
  },
  filters: {},
};
</script>

<style scoped>
.tes {
  width: 28px;
  height: 28px;
  background-color: red;
}
.bg_container {
  background-color: rgb(157, 216, 255);
}
.bubblebox {
  position: relative;
  display: flex;
  justify-content: space-around;
  top: 100%;
}
.bubble {
  display: block;
  transition-duration: 0.08s;
  width: 30px;
  height: 30px;
  border-radius: 100%;
  box-shadow: 0px 0px 15px 0px rgba(255, 255, 255, 0.6) inset;
  -webkit-box-shadow: 0px 0px 15px 0px rgba(255, 255, 255, 0.6) inset;
  position: relative;
}

.bubble:after {
  content: "";
  display: block;
  width: 20%;
  height: 20%;
  border-radius: 100%;
  background: rgba(255, 255, 255, 0.8);
  position: absolute;
  right: 15%;
  top: 15%;
  filter: blur(2px);
  -webkit-filter: blur(2px);
  transform: rotateZ(45deg) scaleY(0.8);
  -webkit-transform: rotateZ(45deg) scaleY(0.8);
}
</style>
