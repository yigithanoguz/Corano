<template>
  <div class="testimonials">
    <div class="container">
      <div class="title">Testimonials</div>
      <div class="sub-title">What they say</div>
      <div class="images">
        <div
          class="img"
          v-for="(item, index) in testimonialsItems"
          :key="index"
          @click="itemIndex = index"
        >
          <img
            :src="item.image"
            alt="..."
            :class="{ scaled: itemIndex === index }"
          />
        </div>
      </div>
      <p class="description">{{ testimonialsItems[itemIndex].description }}</p>
      <div class="voting">
        <i class="bi bi-star" v-for="n in 5" :key="n"></i>
      </div>
      <div class="name">{{ testimonialsItems[itemIndex].name }}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: "testimonials",
  data() {
    return {
      itemIndex: 1,
      testimonialsItems: [
        {
          name: "Lindsy Niloms",
          image:
            "https://htmldemo.net/corano/corano/assets/img/testimonial/testimonial-1.png",
          description:
            "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.",
        },
        {
          name: "Daisy Millan",
          image:
            "https://htmldemo.net/corano/corano/assets/img/testimonial/testimonial-2.png",
          description:
            "Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.",
        },
        {
          name: "Anamika Lusy",
          image:
            "https://htmldemo.net/corano/corano/assets/img/testimonial/testimonial-3.png",
          description:
            "Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.",
        },
      ],
    };
  },
  methods: {},
};
</script>

<style lang="scss" scoped>
.scaled {
  transform: scale(1.3);
}

@keyframes shine {
  0% {
    background-position: -500%;
  }
  100% {
    background-position: 100%;
  }
}

.testimonials {
  height: auto;
  width: 100%;
  padding: 80px;
  background-image: url(https://htmldemo.net/corano/corano/assets/img/testimonial/testimonials-bg.jpg);
  background-position: center;
  background-repeat: no-repeat;
  .container {
    margin: 0 auto;
    height: 100%;
    width: 75%;
    display: flex;
    flex-direction: column;
    align-items: center;
    .title {
      font-size: 2rem;
      font-weight: 700;
      color: #222222;
      // background: linear-gradient(90deg, #c29958, #000, #c29958);
      // background-size: 90%;
      // animation: shine 3s linear infinite;
      // background-clip: text;
      // -webkit-text-fill-color: rgba(255, 255, 255, 0);
      // -webkit-text-size-adjust: 100%;
      // -webkit-tap-highlight-color: transparent;
    }
    .sub-title {
      margin-top: 10px;
      font-size: 0.9rem;
      color: #555555;
    }
    .images {
      margin-top: 40px;
      display: flex;
      gap: 30px;
      .img {
        img {
          width: 70px;
          cursor: pointer;
          transition: all 300ms ease;
        }
      }
    }
    .description {
      color: #555555;
      margin-top: 30px;
      font-size: 0.9rem;
    }
    .voting {
      margin-top: 40px;
      display: flex;
      gap: 5px;
      color: #f9bd22;
    }
    .name {
      margin-top: 10px;
      font-weight: 700;
      color: #000;
    }
  }
}
</style>
