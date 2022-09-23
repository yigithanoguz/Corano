<template>
  <div class="brand-slider">
    <div class="container">
      <div class="brand-group" :style="{ left: `calc(${left}px` }">
        <div
          class="brand"
          v-for="(item, index) in logos"
          :key="index"
          :style="{
            width: (windowWidth * 0.75) / cardCountOnScreen - 10 + 'px',
          }"
        >
          <img :src="item" alt="" />
        </div>
      </div>
    </div>
    <button class="btn-prev">
      <i class="bi bi-chevron-left" @click="slideLeft"></i>
    </button>
    <button class="btn-next" @click="slideRight">
      <i class="bi bi-chevron-right"></i>
    </button>
  </div>
</template>

<script>
export default {
  name: "brand-slider",
  data() {
    return {
      windowWidth: window.innerWidth,
      cardCountOnScreen: 5,
      cardIndex: 0,
      left: 0,
      logos: [
        "https://htmldemo.net/corano/corano/assets/img/brand/1.png",
        "https://htmldemo.net/corano/corano/assets/img/brand/2.png",
        "https://htmldemo.net/corano/corano/assets/img/brand/3.png",
        "https://htmldemo.net/corano/corano/assets/img/brand/4.png",
        "https://htmldemo.net/corano/corano/assets/img/brand/5.png",
        "https://htmldemo.net/corano/corano/assets/img/brand/1.png",
        "https://htmldemo.net/corano/corano/assets/img/brand/2.png",
        "https://htmldemo.net/corano/corano/assets/img/brand/3.png",
        "https://htmldemo.net/corano/corano/assets/img/brand/4.png",
        "https://htmldemo.net/corano/corano/assets/img/brand/5.png",
      ],
    };
  },
  methods: {
    windowWidthControl() {
      this.windowWidth = window.innerWidth;
    },
    slideLeft() {
      if (this.cardIndex === 0) {
        this.cardIndex = this.logos.length - this.cardCountOnScreen;
        this.left -=
          ((this.windowWidth * 0.75) / this.cardCountOnScreen) * this.cardIndex;
      } else {
        this.cardIndex--;
        this.left += (this.windowWidth * 0.75) / this.cardCountOnScreen;
      }
    },
    slideRight() {
      if (this.cardIndex === this.logos.length - this.cardCountOnScreen) {
        this.cardIndex = 0;
        this.left = 0;
      } else {
        this.cardIndex++;
        this.left -= (this.windowWidth * 0.75) / this.cardCountOnScreen;
      }
    },
  },
  mounted() {
    window.addEventListener("resize", this.windowWidthControl);
  },
};
</script>

<style lang="scss" scoped>
$color-gold: #c29958;

.brand-slider {
  width: 100%;
  @media (max-width: 992px) {
    display: none;
  }
  margin-bottom: 100px;
  position: relative;
  &:hover {
    button {
      opacity: 1;
      &.btn-prev {
        left: 70px;
      }
      &.btn-next {
        right: 70px;
      }
    }
  }
  .container {
    height: 100px;
    margin: 0 auto;
    width: 75%;
    border-top: solid 1px #efefef;
    border-bottom: solid 1px #efefef;
    display: flex;
    align-items: center;
    position: relative;
    overflow: hidden;
    .brand-group {
      display: flex;
      gap: 10px;
      position: absolute;
      transition: all 400ms ease;
      .brand {
        // border: solid 1px red;
        img {
          width: 100%;
          cursor: pointer;
        }
      }
    }
  }
  button {
    opacity: 0;
    height: 50px;
    width: 50px;
    font-size: 2rem;
    background-color: transparent;
    color: #777777;
    border: none;
    transition: all 400ms ease;
    z-index: 3;
    cursor: pointer;
    top: 20px;
    position: absolute;
    &:hover {
      color: $color-gold;
    }
    &.btn-prev {
      left: 10px;
    }
    &.btn-next {
      right: 10px;
    }
  }
}
</style>
