<template>
  <div class="latest-blogs">
    <div class="container">
      <div class="title">Latest Blogs</div>
      <div class="sub-title">There are latest blog posts</div>
      <button class="btn-prev">
        <i class="bi bi-chevron-left" @click="slideLeft"></i>
      </button>
      <button class="btn-next" @click="slideRight">
        <i class="bi bi-chevron-right"></i>
      </button>
      <div class="blogs-container">
        <div class="blog-group" :style="{ left: `calc(${left}px` }">
          <div
            class="blog-post"
            :style="{ minWidth: (windowWidth * 0.75) / 3 - 20 + 'px' }"
            v-for="(item, index) in blogs"
            :key="index"
          >
            <div class="image">
              <img
                :src="item.img"
                alt="..."
              />
            </div>
            <div class="blog-date">{{ item.date }} | <a>Corano</a></div>
            <div class="blog-title">
              {{ index }}{{ item.title }}
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "latest-blogs",
  data() {
    return {
      windowWidth: window.innerWidth,
      cardCountOnScreen: 3,
      cardIndex: 0,
      // itemCountOnArray: this.blogs.length,
      left: 0,
      blogs: [
        {
          title: "Children Left Homa Alone For 4 Days In TV Series Experiment",
          date: "25/03/2019",
          img: "https://htmldemo.net/corano/corano/assets/img/blog/blog-img1.jpg",
          description:
            "Children Left Homa Alone For 4 Days In TV Series Experiment. Children Left Homa Alone For 4 Days In TV Series Experiment. Children Left Homa Alone For 4 Days In TV Series Experiment",
        },
        {
          title: "Children Left Homa Alone For 4 Days In TV Series Experiment",
          date: "25/03/2019",
          img: "https://htmldemo.net/corano/corano/assets/img/blog/blog-img2.jpg",
          description:
            "Children Left Homa Alone For 4 Days In TV Series Experiment. Children Left Homa Alone For 4 Days In TV Series Experiment. Children Left Homa Alone For 4 Days In TV Series Experiment",
        },
        {
          title: "Children Left Homa Alone For 4 Days In TV Series Experiment",
          date: "25/03/2019",
          img: "https://htmldemo.net/corano/corano/assets/img/blog/blog-img3.jpg",
          description:
            "Children Left Homa Alone For 4 Days In TV Series Experiment. Children Left Homa Alone For 4 Days In TV Series Experiment. Children Left Homa Alone For 4 Days In TV Series Experiment",
        },
        {
          title: "Children Left Homa Alone For 4 Days In TV Series Experiment",
          date: "25/03/2019",
          img: "https://htmldemo.net/corano/corano/assets/img/blog/blog-img4.jpg",
          description:
            "Children Left Homa Alone For 4 Days In TV Series Experiment. Children Left Homa Alone For 4 Days In TV Series Experiment. Children Left Homa Alone For 4 Days In TV Series Experiment",
        },
        {
          title: "Children Left Homa Alone For 4 Days In TV Series Experiment",
          date: "25/03/2019",
          img: "https://htmldemo.net/corano/corano/assets/img/blog/blog-img5.jpg",
          description:
            "Children Left Homa Alone For 4 Days In TV Series Experiment. Children Left Homa Alone For 4 Days In TV Series Experiment. Children Left Homa Alone For 4 Days In TV Series Experiment",
        },
        {
          title: "Children Left Homa Alone For 4 Days In TV Series Experiment",
          date: "25/03/2019",
          img: "https://htmldemo.net/corano/corano/assets/img/blog/blog-img2.jpg",
          description:
            "Children Left Homa Alone For 4 Days In TV Series Experiment. Children Left Homa Alone For 4 Days In TV Series Experiment. Children Left Homa Alone For 4 Days In TV Series Experiment",
        },
      ],
    };
  },
  methods: {
    windowWidthControl() {
      this.windowWidth = window.innerWidth;
    },
    slideLeft() {
      if (this.cardIndex === 0) {
        this.cardIndex = this.blogs.length - this.cardCountOnScreen;
        this.left -= ((this.windowWidth * 0.75) / 3) * this.cardIndex;
      } else {
        this.cardIndex--;
        this.left += (this.windowWidth * 0.75) / 3;
      }
    },
    slideRight() {
      if (this.cardIndex === this.blogs.length - this.cardCountOnScreen) {
        this.cardIndex = 0;
        this.left = 0;
      } else {
        this.cardIndex++;
        this.left -= (this.windowWidth * 0.75) / 3;
      }
    },
  },
  mounted() {
    window.addEventListener("resize", this.windowWidthControl);
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

.latest-blogs {
  width: 100%;
  padding-top: 80px;
  padding-bottom: 80px;
  .container {
    width: 75%;
    margin: 0 auto;
    position: relative;
    &:hover {
      button {
        opacity: 1;
        &.btn-prev {
          left: -50px;
        }
        &.btn-next {
          right: -50px;
        }
      }
    }
    .title {
      font-size: 2rem;
      font-weight: 700;
    }
    .sub-title {
      margin-top: 10px;
      color: #555555;
    }
    .blogs-container {
      height: 350px;
      margin-top: 40px;
      position: relative;
      overflow: hidden;
    }
    .blog-group {
      display: flex;
      gap: 20px;
      position: absolute;
      width: 100%;
      transition: all 400ms ease;
      .blog-post {
        text-align: left;
        .image {
          overflow: hidden;
          img {
            width: 100%;
            transition: all 400ms ease;
            cursor: pointer;
            &:hover {
              transform: scale(1.2);
              opacity: 0.7;
            }
          }
        }
        .blog-date {
          margin-top: 10px;
          font-size: 0.8rem;
          color: #777777;
          cursor: default;
          a {
            color: $color-gold;
            cursor: pointer;
          }
        }
        .blog-title {
          margin-top: 15px;
          font-size: 1.1rem;
          font-weight: 700;
          cursor: pointer;
          transition: all 400ms ease;
          &:hover {
            color: $color-gold;
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
      color: $color-slide-button;
      border: none;
      transition: all 400ms ease;
      z-index: 3;
      cursor: pointer;
      top: 50%;
      position: absolute;
      &:hover {
        color: $color-gold;
      }
    }
    button.btn-prev {
      left: 5px;
    }
    button.btn-next {
      right: 5px;
    }
  }
}
</style>
