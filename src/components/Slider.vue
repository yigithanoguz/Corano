<template>
  <div
    class="slider"
    :style="{ 'background-image': `url(${slider[item].imgLink})` }"
  >
    <div class="container" v-for="(sliderItem, index) in slider" :key="index">
      <div
        class="slider-title animate__animated animate__heartBeat"
        v-if="item === index"
      >
        {{ sliderItem.title }}
      </div>
      <div
        class="slider-info animate__animated animate__bounceInLeft"
        v-if="item === index"
      >
        {{ sliderItem.infoText }}
      </div>
      <button
        class="slider-btn animate__animated animate__bounceInUp"
        v-if="item === index"
      >
        Read More
      </button>
    </div>
    <!-- <div class="slide-1">
      <div class="container">
        <div class="slider-title">{{ slider[0].title }}</div>
        <div class="slider-info">{{ slider[0].infoText }}</div>
        <button>Read More</button>
      </div>
    </div>
    <div class="slide-2">
      <div class="container">
        <div class="slider-title">{{ slider[1].title }}</div>
        <div class="slider-info">{{ slider[1].infoText }}</div>
        <button>Read More</button>
      </div>
    </div>
    <div class="slide-3">
      <div class="container">
        <div class="slider-title">{{ slider[2].title }}</div>
        <div class="slider-info">{{ slider[2].infoText }}</div>
        <button>Read More</button>
      </div>
    </div> -->
    <!-- :style="{ 'background-image': `url(${slider[item].imgLink})` }" -->
    <button class="prev-button" @click="item--">
      <i class="bi bi-chevron-left"></i>
    </button>
    <button class="next-button" @click="item++">
      <i class="bi bi-chevron-right"></i>
    </button>
  </div>
</template>

<script>
export default {
  name: "slider",
  data() {
    return {
      // isActive: true,
      // animationIterationCount: 1,
      item: 0,
      slider: [
        {
          id: 1,
          title: "Pearls Spring Collection",
          imgLink:
            "https://htmldemo.net/corano/corano/assets/img/slider/home3-slide1.jpg",
          infoText: "New pearl earrings and more from $99",
          // animationName: "",
        },
        {
          id: 2,
          title: "Diamonds Jewelry Collection",
          imgLink:
            "https://htmldemo.net/corano/corano/assets/img/slider/home3-slide2.jpg",
          infoText: "Shukra Yogam & Silver Power Silver Saving Schemes.",
          // animationName: "",
        },
        {
          id: 3,
          title: "Family Spring Collection",
          imgLink:
            "https://htmldemo.net/corano/corano/assets/img/slider/home3-slide3.jpg",
          infoText: "Designer Jewelry Necklaces-Bracelets-Earings",
          // animationName: "",
        },
      ],
    };
  },
  methods: {
    slide() {
      setInterval(() => {
        this.item++;
      }, 5000);
    },
    // animation() {
    //   let margin = 200;
    //   let opacity = 0;
    //   let interval = setInterval(() => {
    //     margin--;
    //     opacity += 0.005;
    //     document.querySelector('.slider-title').style.marginLeft = margin + 'px';
    //     document.querySelector('.slider-title').style.opacity = opacity;
    //     document.querySelector('.slider-info').style.marginLeft = 0 - margin + 'px';
    //     document.querySelector('.slider-info').style.marginTop = margin + 'px';
    //     document.querySelector('.slider-info').style.opacity = opacity;
    //     if(margin === 0) {
    //       clearInterval(interval);
    //     }
    //   }, 1);
    // },
  },
  mounted() {
    this.slide();
    // this.animation();
  },
  watch: {
    item(value) {
      if (value === 3) {
        this.item = 0;
      }
      if (value === -1) {
        this.item = 2;
      }
      // this.animation();
    },
  },
};
</script>

<style lang="scss" scoped>
$color-bg: #f4f4f4;
$color-text: #555555;
$color-white: #fff;
$color-black: #000;
$color-gold: #c29958;
$color-border: #efefef;
$color-bg-search: #f7f7f7;
$color-border-search: #ddd;
$color-slide-button: #777777;

@keyframes scroll-down {
  from {
    opacity: 0;
    margin-left: 100px;
  }
  to {
    opacity: 1;
    margin-left: 0px;
  }
}
@keyframes scroll-downn {
  from {
    opacity: 0;
    margin-left: 100px;
  }
  to {
    opacity: 1;
    margin-left: 0px;
  }
}

.slider {
  height: 530px;
  @media (max-width: 992px) {
    height: 400px;
  }
  @media (max-width: 768px) {
    filter: opacity(0.5);
  }
  width: 100%;
  position: relative;
  display: flex;
  justify-content: space-between;
  align-items: center;
  transition: all 400ms;
  padding: 0px;
  background-size: cover;
  background-position: center;
  overflow: hidden;

  &:hover {
    padding: 0 20px;
    > button {
      opacity: 1;
    }
  }
  > button {
    opacity: 0;
    height: 50px;
    width: 50px;
    font-size: 2rem;
    background-color: transparent;
    color: $color-slide-button;
    border: none;
    transition: all 400ms;
    &:hover {
      color: $color-gold;
    }
    z-index: 3;
    cursor: pointer;
  }
  .container {
    height: 100%;
    width: 75%;
    margin: 0 auto;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: flex-start;
    position: absolute;
    top: 0;
    left: 12.5%;
    gap: 25px;
    .slider-title {
      width: 50%;
      font-size: 3.7rem;
      @media (max-width: 992px) {
        font-size: 3rem;
      }
      @media (max-width: 768px) {
        width: 80%;
      }
      text-align: left;
      color: $color-black;
      line-height: 60px;
      user-select: none;
      // animation-name: scroll-down;
      // animation-duration: 2s;
    }
    .slider-info {
      font-size: 1.2rem;
      font-weight: 300;
      color: $color-black;
      user-select: none;
      @media (max-width: 992px) {
        font-size: 1rem;
      }
    }
    button.slider-btn {
      height: 43px;
      width: 130px;
      margin-top: 10px;
      color: $color-white;
      background-color: $color-gold;
      border: none;
      border-radius: 30px;
      font-size: 0.9rem;
      cursor: pointer;
      transition: 400ms;
      &:hover {
        background-color: $color-black;
      }
    }
  }
}

// .slide-1 {
//   height: 100%;
//   width: 100%;
//   background-image: url(https://htmldemo.net/corano/corano/assets/img/slider/home3-slide1.jpg);
//   background-size: cover;
//   transition: all 400ms;
//   position: absolute;
//   top: 0;
//   left: 0;
// }
// .slide-2 {
//   height: 100%;
//   width: 100%;
//   background-image: url(https://htmldemo.net/corano/corano/assets/img/slider/home3-slide2.jpg);
//   background-size: cover;
//   transition: all 400ms;
//   position: absolute;
//   top: 0;
//   left: 0;
// }
// .slide-3 {
//   height: 100%;
//   width: 100%;
//   background-image: url(https://htmldemo.net/corano/corano/assets/img/slider/home3-slide2.jpg);
//   background-size: cover;
//   transition: all 400ms;
//   position: absolute;
//   top: 0;
//   left: 0;
// }
</style>
