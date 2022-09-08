<template>
  <div class="home">
    <!-- <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <TopBar />
    <Header />
    <Slider />
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
import TopBar from '@/components/TopBar.vue'
import Header from '@/components/Header.vue'
import Slider from '@/components/Slider.vue'

export default {
  name: 'Home',
  components: {
    // HelloWorld
    TopBar,
    Header,
    Slider
  }
}
</script>
