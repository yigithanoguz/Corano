<template>
  <div class="our-products">
    <div class="container">
      <div class="title">Our Products</div>
      <div class="sub-title">Add our products to weekly lineup</div>
      <ul>
        <li>
          <a class="selected"> Entertainment </a>
        </li>
        <li>
          <a> Storage </a>
        </li>
        <li>
          <a> Lying </a>
        </li>
        <li>
          <a> Tables </a>
        </li>
      </ul>
      <div class="slider-buttons">
        <div class="slider">
          <div
            class="cards"
            :style="{ left: `calc(${left}% - ${cardIndex * 5}px)` }"
          >
            <div class="card" v-for="(item, index) in products" :key="index">
              <div class="product-image">
                <img :src="item.imageLink" alt="..." />
                <span class="product-case"> {{ item.case }} </span>
                <span class="product-discount"
                  >{{ item.discountPrice * 100 }}%</span
                >
                <button class="favorites">
                  <i class="bi bi-suit-heart"></i>
                </button>
                <button class="details"><i class="bi bi-search"></i></button>
                <button class="add-to-cart">Add To Cart</button>
              </div>
              <div class="product-info">
                <div class="product-type">{{ item.type }}</div>
                <ul class="product-colors">
                  <li>
                    <a></a>
                  </li>
                  <li>
                    <a></a>
                  </li>
                  <li>
                    <a></a>
                  </li>
                  <li>
                    <a></a>
                  </li>
                </ul>
                <div class="product-name">{{ item.name }}</div>
                <div class="product-price">
                  <span class="sale-price"
                    >${{ (item.price * item.discountPrice).toFixed(2) }}</span
                  >
                  <span class="real-price">${{ item.price.toFixed(2) }}</span>
                </div>
              </div>
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
    </div>
  </div>
</template>

<script>
export default {
  name: "our-products",
  props: {
    products: {
      type: Array,
    },
  },
  data() {
    return {
      cardCountOnScreen: 4,
      cardIndex: 0,
      itemCountOnArray: this.products.length,
      left: 0,
    };
  },
  methods: {
    slideLeft() {
      if (this.cardIndex === 0) {
        this.cardIndex = this.itemCountOnArray - this.cardCountOnScreen;
        this.left -= 25 * this.cardIndex;
      } else {
        this.cardIndex--;
        this.left += 25;
      }
    },
    slideRight() {
      if (this.itemCountOnArray - this.cardCountOnScreen === this.cardIndex) {
        this.cardIndex = 0;
        this.left = 0;
      } else {
        this.cardIndex++;
        this.left -= 25;
      }
    },

  },
  mounted() {
    setInterval(() => {
        this.slideRight();
      }, 5000);
  },
  // watch: {
  //   cardIndex(value) {
  //     console.log(value);
  //   },
  // },
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

.our-products {
  height: 630px;
  width: 100%;
  padding-top: 80px;

  .container {
    height: 100%;
    width: 75%;
    margin: 0 auto;
    display: flex;
    flex-direction: column;
    align-items: center;
    .title {
      font-size: 2rem;
      font-weight: 700;
    }
    .sub-title {
      margin-top: 10px;
      color: #555555;
    }
    ul {
      margin-top: 30px;
      display: flex;
      gap: 50px;
      li {
        a {
          color: #777777;
          &.selected {
            color: #222222;
          }
        }
      }
    }
    .slider-buttons {
      // border: solid 1px blue;
      height: 100%;
      width: 100%;
      position: relative;
      &:hover {
        > button {
          opacity: 1;
        }
        .btn-prev {
          left: -50px;
        }
        .btn-next {
          right: -50px;
        }
      }
      .slider {
        height: 100%;
        width: 100%;
        margin-top: 30px;
        position: relative;
        overflow: hidden;
        .cards {
          height: 100%;
          width: 100%;
          position: absolute;
          top: 0;
          display: flex;
          gap: 20px;
          transition: all 400ms ease;
          .card {
            min-width: calc(25% - 15px);
            display: flex;
            flex-direction: column;
            user-select: none;
            .product-image {
              position: relative;
              cursor: pointer;
              display: flex;
              flex-direction: column;
              &:hover {
                .favorites,
                .details {
                  transform: scale(1.5);
                  opacity: 1;
                }
                .add-to-cart {
                  opacity: 1;
                  bottom: 15px;
                }
              }
              img {
                width: 100%;
                // object-fit: cover;
              }
              .product-case {
                height: 22px;
                width: 44px;
                position: absolute;
                top: 10px;
                left: 10px;
                display: flex;
                justify-content: center;
                align-items: center;
                background-color: $color-gold;
                color: $color-white;
                border-radius: 14px;
                font-size: 0.8rem;
                cursor: default;
              }
              .product-discount {
                height: 22px;
                width: 44px;
                position: absolute;
                top: 40px;
                left: 10px;
                display: flex;
                justify-content: center;
                align-items: center;
                background-color: $color-black;
                color: $color-white;
                border-radius: 14px;
                font-size: 0.8rem;
                cursor: default;
              }
              .favorites {
                height: 25px;
                width: 25px;
                display: flex;
                justify-content: center;
                align-items: center;
                position: absolute;
                top: 20px;
                right: 20px;
                border: none;
                border-radius: 50%;
                background-color: white;
                cursor: pointer;
                transition: all ease 400ms;
                opacity: 0;
                color: #777777;

                &:hover {
                  color: $color-gold;
                }
              }
              .details {
                height: 25px;
                width: 25px;
                display: flex;
                justify-content: center;
                align-items: center;
                position: absolute;
                top: 65px;
                right: 20px;
                border: none;
                border-radius: 50%;
                background-color: white;
                cursor: pointer;
                transition: all ease 400ms;
                opacity: 0;
                color: #777777;
                &:hover {
                  color: $color-gold;
                }
              }
              .add-to-cart {
                height: 40px;
                width: 120px;
                border: none;
                border-radius: 20px;
                cursor: pointer;
                position: absolute;
                bottom: 0;
                align-self: center;
                transition: all 400ms ease;
                background-color: $color-white;
                opacity: 0;
                box-shadow: rgba(0, 0, 0, 0.16) 0px 3px 6px,
                  rgba(0, 0, 0, 0.23) 0px 3px 6px;
                &:hover {
                  background-color: $color-gold;
                  color: $color-white;
                }
              }
            }
            .product-info {
              display: flex;
              flex-direction: column;
              justify-content: center;
              align-items: center;
              gap: 15px;
              padding: 10px 0;
              .product-type {
                color: #777777;
                transition: 400ms all ease;
                cursor: pointer;
                &:hover {
                  color: $color-gold;
                }
              }
              ul.product-colors {
                margin: 0 !important;
                display: flex;
                gap: 5px;
                li {
                  padding: 1px;
                  border-radius: 50%;
                  display: flex;
                  justify-content: center;
                  align-items: center;
                  border: solid 1px gray;
                  transition: 400ms all ease;
                  &:nth-child(1) {
                    a {
                      background-color: #b0c4de;
                    }
                  }
                  &:nth-child(2) {
                    a {
                      background-color: #aa9e78;
                    }
                  }
                  &:nth-child(3) {
                    a {
                      background-color: #808080;
                    }
                  }
                  &:nth-child(4) {
                    a {
                      background-color: #964b00;
                    }
                  }
                  &:hover {
                    border: solid 1px $color-gold;
                  }
                  a {
                    border-radius: 50%;
                    display: inline-block;
                    height: 10px;
                    width: 10px;
                    cursor: pointer;
                  }
                }
              }
              .product-name {
                color: #555555;
                cursor: pointer;
                transition: all 400ms ease;
                &:hover {
                  color: $color-gold;
                }
              }
              .product-price {
                display: flex;
                gap: 10px;
                .sale-price {
                  color: $color-gold;
                }
                .real-price {
                  color: #777777;
                  text-decoration: line-through;
                }
              }
            }
          }
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
        top: 45%;
      }
      button.btn-prev {
        position: absolute;
        left: 5px;
      }
      button.btn-next {
        position: absolute;
        right: 5px;
      }
    }
  }
}
</style>
