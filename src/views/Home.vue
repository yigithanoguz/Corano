<template>
  <div class="home">
    <!-- <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <TopBar />
    <Header @onCart="showCart = $event" :productCount="cart.length" />
    <Slider />
    <AboutUs />
    <our-products :products="products" @addToCart="productIndex = $event" @data="data = $event" />
    <carousel />
    <featured-products :products="products" />
    <testimonials />
    <other-products :products="products" />
    <LatestBlogs />
    <brand-slider />
    <Footer />
    <SidebarCart :showCart="showCart" @hideCart="showCart = $event" :cart="cart" :totalPrice="totalPrice" />
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
import TopBar from "@/components/TopBar.vue";
import Header from "@/components/Header.vue";
import Slider from "@/components/Slider.vue";
import AboutUs from "@/components/AboutUs.vue";
import OurProducts from "@/components/OurProducts.vue";
import Carousel from "@/components/Carousel.vue";
import FeaturedProducts from "@/components/FeaturedProducts.vue";
import Testimonials from "../components/Testimonials.vue";
import OtherProducts from "../components/OtherProducts.vue";
import LatestBlogs from "../components/LatestBlogs.vue";
import BrandSlider from "../components/BrandSlider.vue";
import Footer from "../components/Footer.vue";
import SidebarCart from "../components/SidebarCart.vue";

export default {
  name: "Home",
  components: {
    // HelloWorld
    TopBar,
    Header,
    Slider,
    AboutUs,
    OurProducts,
    Carousel,
    FeaturedProducts,
    Testimonials,
    OtherProducts,
    LatestBlogs,
    BrandSlider,
    Footer,
    SidebarCart,
  },
  data() {
    return {
      showCart: null,
      data: false,
      productIndex: null,
    };
  },
  props: {
    products: {
      type: Array,
    },
    cart: {
      type: Array,
    },
    totalPrice: {
      type: Number,
    }
  },
  watch: {
    // showCart(value) {
    //   // this.$emit('showCart', value);
    //   // console.log('showCart: ' + value)
    // },
    data() {
      if(this.data === true) {
        this.data = false;
        this.$emit('addToCart', this.productIndex);
        this.$emit('data', true);
      }
    }
  },
  // computed: {
  //   test() {
  //     return console.log('test')
  //   }
  // },
};
</script>

<style lang="scss" scoped>

// .home {
//   overflow: hidden;
//   width: 100vw;
// }
</style>
