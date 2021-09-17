<template>
  <div id="header">
    <!-- Header top links -->
    <section id="top-header">
      <div class="container d-flex align-items-center py-3">
        <h6 class="m-0">Everything about Lifestyle, Travel and Gadgets!</h6>

        <ul class="d-flex m-0">
          <li v-for="(link, index) in topHeaderLinks" :key="index" class="mx-3">
            <a :href="link.url">{{ link.text }}</a>
          </li>
        </ul>
      </div>
    </section>

    <!-- Mid header section (LOGO) -->
    <section id="logo">
      <div class="container py-3">
        <img src="../assets/images/logo-default-slim.png" alt="Logo" />
      </div>
    </section>

    <!-- Divider -->
    <hr class="m-0" />

    <!-- Navbar and search -->
    <section id="navbar">
      <div
        class="container d-flex align-items-center justify-content-between py-3"
      >
        <ul class="d-flex m-0 p-0">
          <li v-for="(link, index) in navbarLinks" :key="index" class="me-5">
            <a :href="link.url">{{ link.text }}</a>
          </li>
        </ul>
        <div>
          <input
            type="text "
            v-show="hidden"
            v-model="searchText"
            class="me-3"
          />
          <button type="button" @click="showSearchbar">
            <i class="fas fa-search"></i>
          </button>
        </div>
      </div>
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
      hidden: false,
      searchText: "",
    };
  },
  methods: {
    showSearchbar() {
      this.hidden = !this.hidden;
    },
  },
};
</script>

<style lang="scss">
@import "@/assets/scss/_colors.scss";
#top-header {
  background-color: $bg-color-primary;
  ul {
    list-style-type: none;
    a {
      text-decoration: none;
      color: $bg-color-white;
    }
  }
  h6 {
    color: $bg-color-white;
  }
}
#navbar {
  ul {
    list-style-type: none;
    li:hover {
      a {
        color: $text-color-primary;
      }
    }
    a {
      text-decoration: none;
      color: $bg-color-black;
      font-weight: bold;
    }
  }
  button {
    background-color: $bg-color-white;
    border: 0px;
  }
}
</style>