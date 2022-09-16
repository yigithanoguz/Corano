<template>
  <div id="app">
    <!-- <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div> -->

    <router-view
      :products="products"
     />
  </div>
</template>

<script>
export default {
  name: 'app',
  data() {
    return {
      products: [
        {
          id: 1,
          name: 'Perfect Diamond Jewelry',
          type: 'Diamond',
          imageLink: 'https://htmldemo.net/corano/corano/assets/img/product/product-1.jpg',
          imageLink2: 'https://htmldemo.net/corano/corano/assets/img/product/product-11.jpg',
          currency: '$',
          price: 99,
          discountPrice: 0.50,
          case: 'New',
        },
        {
          id: 2,
          name: 'Perfect Diamond Jewelry',
          type: 'Diamond',
          imageLink: 'https://htmldemo.net/corano/corano/assets/img/product/product-2.jpg',
          imageLink2: 'https://htmldemo.net/corano/corano/assets/img/product/product-12.jpg',
          currency: '$',
          price: 99,
          discountPrice: 0.50,
          case: 'New',
        },
        {
          id: 3,
          name: 'Perfect Diamond Jewelry',
          type: 'Diamond',
          imageLink: 'https://htmldemo.net/corano/corano/assets/img/product/product-3.jpg',
          imageLink2: 'https://htmldemo.net/corano/corano/assets/img/product/product-13.jpg',
          currency: '$',
          price: 99,
          discountPrice: 0.50,
          case: 'New',
        },
        {
          id: 4,
          name: 'Perfect Diamond Jewelry',
          type: 'Diamond',
          imageLink: 'https://htmldemo.net/corano/corano/assets/img/product/product-4.jpg',
          imageLink2: 'https://htmldemo.net/corano/corano/assets/img/product/product-14.jpg',
          currency: '$',
          price: 99,
          discountPrice: 0.50,
          case: 'New',
        },
        {
          id: 5,
          name: 'Perfect Diamond Jewelry',
          type: 'Diamond',
          imageLink: 'https://htmldemo.net/corano/corano/assets/img/product/product-5.jpg',
          imageLink2: 'https://htmldemo.net/corano/corano/assets/img/product/product-15.jpg',
          currency: '$',
          price: 99,
          discountPrice: 0.50,
          case: 'New',
        },
        {
          id: 6,
          name: 'Perfect Diamond Jewelry',
          type: 'Diamond',
          imageLink: 'https://htmldemo.net/corano/corano/assets/img/product/product-6.jpg',
          imageLink2: 'https://htmldemo.net/corano/corano/assets/img/product/product-16.jpg',
          currency: '$',
          price: 99,
          discountPrice: 0.50,
          case: 'New',
        },{
          id: 5,
          name: 'Perfect Diamond Jewelry',
          type: 'Diamond',
          imageLink: 'https://htmldemo.net/corano/corano/assets/img/product/product-5.jpg',
          imageLink2: 'https://htmldemo.net/corano/corano/assets/img/product/product-15.jpg',
          currency: '$',
          price: 99,
          discountPrice: 0.50,
          case: 'New',
        },
        {
          id: 6,
          name: 'Perfect Diamond Jewelry',
          type: 'Diamond',
          imageLink: 'https://htmldemo.net/corano/corano/assets/img/product/product-6.jpg',
          imageLink2: 'https://htmldemo.net/corano/corano/assets/img/product/product-16.jpg',
          currency: '$',
          price: 99,
          discountPrice: 0.50,
          case: 'New',
        },
        {
          id: 5,
          name: 'Perfect Diamond Jewelry',
          type: 'Diamond',
          imageLink: 'https://htmldemo.net/corano/corano/assets/img/product/product-5.jpg',
          imageLink2: 'https://htmldemo.net/corano/corano/assets/img/product/product-15.jpg',
          currency: '$',
          price: 99,
          discountPrice: 0.50,
          case: 'New',
        },
        {
          id: 6,
          name: 'Perfect Diamond Jewelry',
          type: 'Diamond',
          imageLink: 'https://htmldemo.net/corano/corano/assets/img/product/product-6.jpg',
          imageLink2: 'https://htmldemo.net/corano/corano/assets/img/product/product-16.jpg',
          currency: '$',
          price: 99,
          discountPrice: 0.50,
          case: 'New',
        }
      ]
    }
  },
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Lato:wght@100;300;400;700;900&display=swap');

$color-gold: #c29958;

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
#app {
  // font-family: Avenir, Helvetica, Arial, sans-serif;
  font-family: 'Lato', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

ul {
  list-style: none;
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
