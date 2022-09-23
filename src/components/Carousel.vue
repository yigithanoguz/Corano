<template>
  <div class="carousel">
    <div
      class="carousel-item"
      v-for="(item, index) in carouselItems"
      :key="index"
      :style="{ left: `calc(${left}% - ${cardIndex * 5}px)` }"
    >
      <div class="image">
        <img :src="item.img" :alt="item.title" />
      </div>
      <div class="title">
        {{ item.title }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "carousel",
  data() {
    return {
      windowWidth: window.innerWidth,
      cardCountOnScreen: 4,
      cardIndex: 0,
      // itemCountOnArray: this.carouselItems.length,
      left: 0,
      carouselItems: [
        {
          title: "Bracelates",
          img: "https://htmldemo.net/corano/corano/assets/img/banner/img1-middle.jpg",
        },
        {
          title: "Earrings",
          img: "https://htmldemo.net/corano/corano/assets/img/banner/img2-middle.jpg",
        },
        {
          title: "Necjlaces",
          img: "https://htmldemo.net/corano/corano/assets/img/banner/img3-middle.jpg",
        },
        {
          title: "Rings",
          img: "https://htmldemo.net/corano/corano/assets/img/banner/img4-middle.jpg",
        },
        {
          title: "Pearls",
          img: "https://htmldemo.net/corano/corano/assets/img/banner/img5-middle.jpg",
        },
      ],
    };
  },
  methods: {
    windowWidthControl() {
      this.windowWidth = window.innerWidth;
      if (this.windowWidth < 768) {
        this.cardCountOnScreen = 2;
      } else if (this.windowWidth < 992) {
        this.cardCountOnScreen = 3;
      } else {
        this.cardCountOnScreen = 4;
      }
    },
    slideLeft() {
      if (this.cardIndex === 0) {
        this.cardIndex = this.carouselItems.length - this.cardCountOnScreen;
        this.left -= (100 / this.cardCountOnScreen) * this.cardIndex;
      } else {
        this.cardIndex--;
        this.left += 100 / this.cardCountOnScreen;
      }
    },
    slideRight() {
      if (
        this.carouselItems.length - this.cardCountOnScreen ===
        this.cardIndex
      ) {
        this.cardIndex = 0;
        this.left = 0;
      } else {
        this.cardIndex++;
        this.left -= 100 / this.cardCountOnScreen;
      }
    },
  },
  mounted() {
    this.windowWidthControl();
    window.addEventListener("resize", this.windowWidthControl);
    setInterval(() => {
      this.slideRight();
    }, 5000);
  },
};
</script>

<style lang="scss" scoped>
.carousel {
  height: 100%;
  padding: 0 10px;
  display: flex;
  gap: 20px;
  overflow: hidden;
  position: relative;
  .carousel-item {
    height: 100%;
    min-width: calc(25% - 15px);
    @media (max-width: 992px) {
      min-width: calc(33.33333% - 15px);
    }
    position: relative;
    transition: all 400ms ease;
    cursor: pointer;
    &:hover {
      .image {
        opacity: 80%;
      }
    }
    .image {
      // width: 100%;
      transition: all 400ms ease;
      img {
        width: 100%;
        user-select: none;
      }
    }
    .title {
      position: absolute;
      left: 40px;
      bottom: 50px;
      font-size: 1.25rem;
      font-weight: 700;
      text-transform: uppercase;
      color: #000;
      transition: 400ms all ease;
      user-select: none;
      &:hover {
        color: #c29958;
      }
    }
  }
}
</style>
