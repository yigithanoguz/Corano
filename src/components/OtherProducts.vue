<template>
  <div class="other-products">
    <div class="container">
      <div class="new-arrivals">
        <div class="top">
          <div class="title">New Arrivals</div>
          <div class="buttons">
            <button class="btn-prev">
              <i class="bi bi-chevron-left" @click="slideLeft"></i>
            </button>
            <button class="btn-next" @click="slideRight">
              <i class="bi bi-chevron-right"></i>
            </button>
          </div>
        </div>
        <div class="products-container">
          <!-- overflow: hidden; -->
          <div class="products-group">
            <div class="product">
              <img src="https://htmldemo.net/corano/corano/assets/img/product/product-1.jpg" alt="..." />
              <div class="product-info">
                <div class="name">Diamond Exclusive Ring</div>
                <div class="product-price">
                  fiyat
                  <!-- <span class="sale-price"
                  >${{ (item.price * item.discountPrice).toFixed(2) }}</span
                >
                <span class="real-price">${{ item.price.toFixed(2) }}</span> -->
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="best-seller-product"></div>
      <div class="on-sale-product"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: "other-products",
  props: {
    products: {
      type: Array,
    },
  },
  data() {
    return {};
  },
  methods: {},
};
</script>

<style lang="scss" scoped>
$color-gold: #c29958;

.other-products {
  width: 100%;
  padding-top: 80px;
  .container {
    width: 75%;
    margin: 0 auto;
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 50px;
    .new-arrivals {
      display: flex;
      flex-direction: column;
      .top {
        display: flex;
        justify-content: space-between;
        align-items: center;
        .title {
          font-size: 1.2rem;
          font-weight: 700;
          color: #000;
        }
        .buttons {
          display: flex;
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
        .products-group {
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
              }
            }
          }
        }
      }
    }
  }
}
</style>
