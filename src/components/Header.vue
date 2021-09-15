<template>
  <div id="header">
    <!-- Header top links -->
    <section id="top-header">
      <h6>Everything about Lifestyle, Travel and Gadgets!</h6>
      <ul v-for="(link, index) in topHeaderLinks" :key="index">
        <li>
          <a :href="link.url">{{ link.text }}</a>
        </li>
      </ul>
    </section>

    <!-- Mid header section (LOGO) -->
    <section id="logo">
      <img src="../assets/images/logo-default-slim.png" alt="Logo" />
    </section>

    <!-- Navbar and search -->
    <section id="navbar">
      <ul v-for="(link, index) in navbarLinks" :key="index">
        <li>
          <a :href="link.url">{{ link.text }}</a>
        </li>
      </ul>
      <button>search</button>
    </section>
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
      navbarLinks: [
        {
          text: "HOME",
          url: "#",
        },
        {
          text: "ELEMENTS",
          url: "#",
        },
        {
          text: "FEATURES",
          url: "#",
        },
        {
          text: "PAGES",
          url: "#",
        },
        {
          text: "PORTFOLIO",
          url: "#",
        },
        {
          text: "BLOG",
          url: "#",
        },
        {
          text: "SHOP",
          url: "#",
        },
      ],
    };
  },
};
</script>

<style scoped lang="scss">
</style>