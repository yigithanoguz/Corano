<template>
  <div class="home">
    <!-- <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <TopBar />
    <Header />
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
import TopBar from '@/components/TopBar.vue'
import Header from '@/components/Header.vue'

export default {
  name: 'Home',
  components: {
    // HelloWorld
    TopBar,
    Header
  }
}
</script>
