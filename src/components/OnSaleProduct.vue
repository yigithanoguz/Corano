<template>
  <div class="on-sale-product">
    <div class="top">
      <div class="title">On-Sale Product</div>
      <div class="buttons">
        <button class="btn-prev" @click="slideLeft">
          <i class="bi bi-chevron-left"></i>
        </button>
        <button class="btn-next" @click="slideRight">
          <i class="bi bi-chevron-right"></i>
        </button>
      </div>
    </div>
    <div class="products-container">
      <div
        class="products-group"
        :style="{ left: `calc( ${left}px - ${columnIndex * 20}px )` }"
      >
        <div
          class="product"
          v-for="(item, index) in products"
          :key="index"
          :style="{
            'grid-row-start': index % 4,
            'grid-row-end': (index % 4) + 1,
            'grid-column-start': Math.floor(index / 4) + 1,
            'grid-column-end': Math.floor(index / 4) + 2,
            width: (windowWidth * 0.75) / 3 - 40 + 'px',
          }"
        >
          <img :src="item.imageLink" alt="..." />
          <div class="product-info">
            <div class="name">{{ item.name }}</div>
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
  </div>
</template>

<script>
export default {
  name: "on-sale-product",
  props: {
    products: {
      type: Array,
    },
  },
  data() {
    return {
      windowWidth: window.innerWidth,
      columnIndex: 0,
      columnCount: Math.ceil(this.products.length / 4),
      left: 0,
    };
  },
  methods: {
    windowWidthControl() {
      this.windowWidth = window.innerWidth;
    },
    slideLeft() {
      if (this.columnIndex === 0) {
        this.columnIndex = this.columnCount - 1;
        this.left -=
          ((this.windowWidth * 0.75) / 3 - 40) * (this.columnCount - 1);
      } else {
        this.columnIndex--;
        this.left += (this.windowWidth * 0.75) / 3 - 40;
      }
    },
    slideRight() {
      if (this.columnIndex === this.columnCount - 1) {
        this.columnIndex = 0;
        this.left = 0;
      } else {
        this.columnIndex++;
        this.left -= (this.windowWidth * 0.75) / 3 - 40;
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

.on-sale-product {
  display: flex;
  flex-direction: column;
  .top {
    display: flex;
    justify-content: space-between;
    align-items: center;
    position: relative;
    overflow: hidden;
    .title {
      font-size: 1.2rem;
      font-weight: 700;
      color: #000;
      &:after {
        content: "";
        height: 2px;
        background-color: #efefef;
        width: 100%;
        position: absolute;
        top: 50%;
        z-index: 1;
        margin-left: 5px;
      }
    }
    .buttons {
      display: flex;
      z-index: 2;
      background-color: #fff;
      button {
        width: 40px;
        background-color: transparent;
        border: none;
        font-size: 1rem;
        cursor: pointer;
        transition: all 400ms ease;
        &:hover {
          color: $color-gold;
        }
      }
    }
  }
  .products-container {
    height: 450px;
    position: relative;
    overflow: hidden;
    .products-group {
      margin-top: 20px;
      position: absolute;
      display: grid;
      column-gap: 20px;
      transition: all 400ms ease;
      top: 0;
      .product {
        padding: 10px 0;
        display: flex;
        gap: 20px;
        img {
          width: 25%;
        }
        .product-info {
          .name {
            margin-top: 5px;
            transition: all 400ms ease;
            cursor: pointer;
            &:hover {
              color: $color-gold;
              text-decoration: underline;
            }
          }
          .product-price {
            margin-top: 20px;
            text-align: left;
            font-size: 0.9rem;
            .sale-price {
              color: $color-gold;
            }
            .real-price {
              margin-left: 10px;
              color: #999999;
              text-decoration: line-through;
            }
          }
        }
      }
    }
  }
}
</style>
