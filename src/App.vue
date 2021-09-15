<template>
  <div>
    <Header />

    <Main />

    <Footer />
  </div>
</template>

<script>
import Header from "../src/components/Header.vue";
import Main from "../src/components/Main.vue";
import Footer from "../src/components/Footer.vue";

export default {
  name: "App",
  components: {
    Header,
    Main,
    Footer,
  },
};
</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
div {
  background-color: #ccc;
}
</style>
