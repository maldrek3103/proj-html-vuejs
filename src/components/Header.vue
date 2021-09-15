<template>
  <div id="header">
    <!-- Header top links -->
    <section id="top-header"></section>

    <!-- Mid header section (LOGO) -->
    <section id="logo"></section>

    <!-- Navbar and search -->
    <section id="navbar"></section>
  </div>
</template>

<script>
// Component export script
export default {
  name: "Header",

  //   Data section
  data() {
    return {
      topHeaderLinks: [
        {
          text: "SIGN IN",
          url: "#",
        },
        {
          text: "ABOUT US",
          url: "#",
        },
        {
          text: "CONTACT US",
          url: "#",
        },
        {
          text: "BUY NOW",
          url: "#",
        },
      ],
    };
  },
};
</script>

<style scoped lang="scss">
</style>