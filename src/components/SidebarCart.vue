<template>
  <div class="sidebar-cart" @click="closeSidebar">
    <transition name="fade"
      ><div class="shadow" v-if="isActive"></div
    ></transition>

    <transition name="slide">
      <div
        class="cart-container"
        v-if="isActive"
        @mouseover="isHover = true"
        @mouseleave="isHover = false"
      >
        <button class="close-button" @click="hideCart">
          <i class="bi bi-x-lg"></i>
        </button>
        <div class="cart-products">
          <div class="product" v-for="(item, index) in cart" :key="index">
            <img :src="item.imageLink" alt="..." />
            <div class="product-info">
              <div class="product-name">
                {{ item.name }}
              </div>
              <div class="product-price">
                <span class="product-count">{{ item.count }} × </span>
                ${{ (item.price * item.discountPrice).toFixed(2) }}
              </div>
            </div>
            <button class="remove-button" @click="removeItem(index)"><i class="bi bi-x-lg"></i></button>
          </div>
        </div>
        <div class="price-info">
          <div class="total-price" v-if="totalPrice !== null">
            Total: ${{ totalPrice.toFixed(2) }}
          </div>
          <div class="total-price" v-else>
            Sepetinizde ürün bulunmamaktadır.
          </div>
        </div>
      </div>
    </transition>
  </div>
</template>

<script>
export default {
  name: "sidebar-cart",
  data() {
    return {
      isActive: false,
      isHover: false,
    };
  },
  props: {
    showCart: {
      type: Boolean,
    },
    cart: {
      type: Array,
    },
    totalPrice: {
      type: Number,
    },
  },
  methods: {
    closeSidebar() {
      if (this.isHover === false) {
        this.hideCart();
      }
    },
    hideCart() {
      this.isActive = false;
    },
    removeItem(index) {
      this.cart.splice(index, 1)
    }
  },
  watch: {
    showCart(value) {
      // console.log(value);
      if (value === true) {
        this.isActive = true;
      } else {
        this.isActive = false;
      }
      // value === true ? (this.isActive = true) : (this.isActive = false);
      // console.log("active");
    },
    isActive(value) {
      if (value === false) {
        this.$emit("hideCart", value);
      }
    },
  },
};
</script>

<style lang="scss" scoped>
$color-gold: #c29958;

.fade-enter {
  opacity: 0;
}
.fade-enter-active {
  transition: opacity 500ms;
}
.fade-leave {
  // opacity: 1;
}
.fade-leave-active {
  transition: opacity 500ms;
  opacity: 0;
}

@keyframes slide-in {
  from {
    transform: translateX(360px);
  }
  to {
    transform: translateX(0px);
  }
}
@keyframes slide-out {
  from {
    transform: translateX(0px);
  }
  to {
    transform: translateX(360px);
  }
}

.slide-enter {
}
.slide-enter-active {
  animation: slide-in 500ms ease;
}
.slide-leave {
}
.slide-leave-active {
  animation: slide-out 500ms ease;
}

.sidebar-cart {
  overflow-x: hidden;
  .shadow {
    height: 100vh;
    width: 100%;
    position: fixed;
    top: 0;
    // right: -100vw;
    left: 0;
    z-index: 99;
    background-color: rgba(0, 0, 0, 0.5);
    cursor: url(https://htmldemo.net/corano/corano/assets/img/icon/cancel.png),
      auto;
    // &.active {
    //   right: 0;
    //   .cart-container {
    //     right: 0;
    //   }
    // }
  }
  .cart-container {
    height: 100%;
    width: 360px;
    padding: 20px;
    overflow-y: auto;
    position: fixed;
    top: 0;
    right: 0;
    // right: -360px;
    z-index: 100;
    background-color: white;
    transition: all 400ms ease;
    cursor: auto;

    .cart-products {
      margin-top: 20px;
      .product {
        padding: 20px 0;
        display: flex;
        gap: 10px;
        border-bottom: 1px solid #efefef;
        position: relative;
        img {
          width: 30%;
        }
        .product-info {
          text-align: left;
          .product-name {
            font-size: 0.9rem;
            font-weight: 700;
            line-height: 24px;
            transition: all 400ms ease;
            cursor: pointer;
            &:hover {
              color: $color-gold;
            }
          }
          .product-price {
            margin-top: 10px;
            font-size: 0.9rem;
            color: $color-gold;
            .product-count {
              font-size: 0.85rem;
              color: #555555;
            }
          }
        }
        .remove-button {
          border: none;
          background-color: transparent;
          position: absolute;
          top: calc(50% - 1rem);
          right: 5px;
          font-size: 1rem;
          cursor: pointer;
          transition: all 400ms ease;;
          &:hover {
            color: $color-gold;
          }
        }
      }
    }
    .price-info {
      text-align: left;
      margin-top: 20px;
      font-size: 1.2rem;
      font-weight: 700;
      .total-price {
      }
    }

    .close-button {
      height: 50px;
      width: 50px;
      position: absolute;
      top: 0;
      left: -50px;
      border: none;
      background-color: $color-gold;
      color: #fff;
      font-size: 1.5rem;
      transition: all 400ms ease;
      cursor: pointer;
      &:hover {
        i.bi {
          &:before {
            transform: rotate(0.5turn);
          }
        }
      }
      i.bi {
        &::before {
          transition: all 500ms ease;
        }
      }
    }
  }
}
</style>
