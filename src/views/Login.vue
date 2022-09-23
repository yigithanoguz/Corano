<template>
  <div class="login">
    <TopBar />
    <Header />
    <h1>LOGIN PAGE</h1>
    <ul>
      <router-link tag="li" to="/">
        <a>Home</a>
      </router-link>
    </ul>
  </div>
</template>

<script>
import Header from "@/components/Header.vue";
import TopBar from "@/components/TopBar.vue";

export default {
  name: "Login",
  components: {
    TopBar,
    Header,
  },
};
</script>

<style lang="scss" scoped>
h1 {
  padding: 30px;
}
</style>
