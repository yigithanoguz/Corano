<template>
  <div class="other-products">
    <div class="container">
      <new-arrivals :products="products" />
      <best-seller-product :products="products" />
      <on-sale-product :products="products" />
    </div>
  </div>
</template>

<script>

import NewArrivals from '@/components/NewArrivals.vue'
import BestSellerProduct from '@/components/BestSellerProduct.vue'
import OnSaleProduct from '@/components/OnSaleProduct.vue'


export default {

  name: "other-products",
  components: {
    NewArrivals,
    BestSellerProduct,
    OnSaleProduct,
  },
  props: {
    products: {
      type: Array,
    },
  },

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

  }
}
</style>
