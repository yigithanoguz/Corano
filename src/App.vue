<template>
  <div id="app">
    <!-- <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div> -->

    <router-view
      :products="products"
      @addToCart="productIndex = $event"
      @data="data = $event"
      :cart="cart"
      :totalPrice="totalPrice"
    />
  </div>
</template>

<script>
export default {
  name: "app",
  data() {
    return {
      productIndex: null,
      data: false,
      isNew: false,
      cart: [],
      totalPrice: null,
      products: [
        {
          id: 1,
          name: "Perfect Diamond Jewelry",
          type: "Diamond",
          imageLink:
            "https://htmldemo.net/corano/corano/assets/img/product/product-1.jpg",
          imageLink2:
            "https://htmldemo.net/corano/corano/assets/img/product/product-11.jpg",
          currency: "$",
          price: 99,
          discountPrice: 0.5,
          case: "New",
        },
        {
          id: 2,
          name: "Perfect Diamond Jewelry",
          type: "Diamond",
          imageLink:
            "https://htmldemo.net/corano/corano/assets/img/product/product-2.jpg",
          imageLink2:
            "https://htmldemo.net/corano/corano/assets/img/product/product-12.jpg",
          currency: "$",
          price: 99,
          discountPrice: 0.5,
          case: "New",
        },
        {
          id: 3,
          name: "Perfect Diamond Jewelry",
          type: "Diamond",
          imageLink:
            "https://htmldemo.net/corano/corano/assets/img/product/product-3.jpg",
          imageLink2:
            "https://htmldemo.net/corano/corano/assets/img/product/product-13.jpg",
          currency: "$",
          price: 99,
          discountPrice: 0.5,
          case: "New",
        },
        {
          id: 4,
          name: "Perfect Diamond Jewelry",
          type: "Diamond",
          imageLink:
            "https://htmldemo.net/corano/corano/assets/img/product/product-4.jpg",
          imageLink2:
            "https://htmldemo.net/corano/corano/assets/img/product/product-14.jpg",
          currency: "$",
          price: 99,
          discountPrice: 0.5,
          case: "New",
        },
        {
          id: 5,
          name: "Perfect Diamond Jewelry",
          type: "Diamond",
          imageLink:
            "https://htmldemo.net/corano/corano/assets/img/product/product-5.jpg",
          imageLink2:
            "https://htmldemo.net/corano/corano/assets/img/product/product-15.jpg",
          currency: "$",
          price: 99,
          discountPrice: 0.5,
          case: "New",
        },
        {
          id: 6,
          name: "Perfect Diamond Jewelry",
          type: "Diamond",
          imageLink:
            "https://htmldemo.net/corano/corano/assets/img/product/product-6.jpg",
          imageLink2:
            "https://htmldemo.net/corano/corano/assets/img/product/product-16.jpg",
          currency: "$",
          price: 99,
          discountPrice: 0.5,
          case: "New",
        },
        {
          id: 5,
          name: "Perfect Diamond Jewelry",
          type: "Diamond",
          imageLink:
            "https://htmldemo.net/corano/corano/assets/img/product/product-5.jpg",
          imageLink2:
            "https://htmldemo.net/corano/corano/assets/img/product/product-15.jpg",
          currency: "$",
          price: 99,
          discountPrice: 0.5,
          case: "New",
        },
        {
          id: 6,
          name: "Perfect Diamond Jewelry",
          type: "Diamond",
          imageLink:
            "https://htmldemo.net/corano/corano/assets/img/product/product-6.jpg",
          imageLink2:
            "https://htmldemo.net/corano/corano/assets/img/product/product-16.jpg",
          currency: "$",
          price: 99,
          discountPrice: 0.5,
          case: "New",
        },
        {
          id: 5,
          name: "Perfect Diamond Jewelry",
          type: "Diamond",
          imageLink:
            "https://htmldemo.net/corano/corano/assets/img/product/product-5.jpg",
          imageLink2:
            "https://htmldemo.net/corano/corano/assets/img/product/product-15.jpg",
          currency: "$",
          price: 99,
          discountPrice: 0.5,
          case: "New",
        },
        {
          id: 6,
          name: "Perfect Diamond Jewelry",
          type: "Diamond",
          imageLink:
            "https://htmldemo.net/corano/corano/assets/img/product/product-6.jpg",
          imageLink2:
            "https://htmldemo.net/corano/corano/assets/img/product/product-16.jpg",
          currency: "$",
          price: 99,
          discountPrice: 0.5,
          case: "New",
        },
      ],
    };
  },
  methods: {
    addToCart() {
      // this.cart.push(this.products[this.productIndex]);

      if (this.cart.length === 0) {
        this.cart.push(this.products[this.productIndex]);
        this.cart[0]["count"] = 1;
        // console.log("ilk eleman eklendi")
      } else {
        // console.log("2 veya sonraki eleman")
        for (let i in this.cart) {
          if (this.cart[i] === this.products[this.productIndex]) {
            this.cart[i]["count"]++;
            // console.log('??r??n??n ayn??s?? sepette var say??s?? artt?? yeni say??: ' + this.cart[i]["count"])
            this.isNew = false;
            break;
          } else {
            this.isNew = true;
            // console.log('??r??n sepette bulunamad??')
          }
        }
        if (this.isNew) {
          // console.log('??r??n sepette bulunamad?????? i??in sepetin sonuna eklendi')
          this.cart.push(this.products[this.productIndex]);
          this.cart[this.cart.length - 1]["count"] = 1;
          this.isNew = false;
        }
      }

      // console.log('reduce')
      this.totalPrice = 0;
      for (let i of this.cart) {
        this.totalPrice += i.price * i.discountPrice * i["count"];
      }
    },
  },
  watch: {
    data() {
      if (this.data === true) {
        this.data = false;
        this.addToCart();
        // console.log("pi: " + this.productIndex);
      }
    },
  },
};
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Lato:wght@100;300;400;700;900&display=swap");

$color-gold: #c29958;

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
#app {
  // font-family: Avenir, Helvetica, Arial, sans-serif;
  font-family: "Lato", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

ul {
  list-style: none;
}

a {
  text-decoration: none;
  // color: red;
}

::selection {
  background-color: $color-gold;
  color: #fff;
}

// #nav {
//   padding: 30px;

//   a {
//     font-weight: bold;
//     color: #2c3e50;

//     &.router-link-exact-active {
//       color: #42b983;
//     }
//   }
// }
</style>
