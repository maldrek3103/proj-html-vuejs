<template>
  <div id="footer">
    <section id="top-footer" class="py-5">
      <div class="container">
        <div class="row">
          <span>Get in Touch</span>
          <!-- About the blog -->
          <div class="col-3">
            <h5>ABOUT THE BLOG</h5>
            <p>
              Lorem ipsum dolor sit amet, consectetur adipisicing elit. Officiis
              consequatur nulla eveniet possimus hic nihil, aliquid earum
              exercitationem corporis ipsam, assumenda modi quia? Voluptas ipsa
              nesciunt magni voluptatum minima saepe.
            </p>
          </div>
          <!-- Recent posts -->
          <div class="col-3">
            <h5>RECENT POSTS</h5>
            <ul v-for="(post, index) in recentPostsFooter" :key="index">
              <li>
                <img :src="post.img" alt="Our office" />
                <h6>{{ post.text }}</h6>
                <p>{{ post.date }}</p>
              </li>
            </ul>
          </div>
          <!-- Recent comments -->
          <div class="col-3">
            <h5>RECENT COMMENTS</h5>
            <ul v-for="(comment, index) in recentCommentsFooter" :key="index">
              <li>
                <h6>
                  {{ comment.author }} commented on
                  <a href="#">{{ comment.text }}</a>
                </h6>
                <p>{{ comment.date }}</p>
              </li>
            </ul>
          </div>
          <!-- Categories -->
          <div class="col-3">
            <h5>CATEGORIES</h5>
            <ul v-for="category in categories" :key="category">
              <li>
                <span class="badge badge-secondary">{{ category }}</span>
              </li>
            </ul>
          </div>
        </div>
      </div>
    </section>
    <section id="bottom-footer" class="py-5">
      <!-- LOGO + Copyright -->
      <div class="container">
        <div class="row justify-content-between align-items-center">
          <div class="col-5">
            <div id="copyright">
              <div class="d-flex align-items-center flex-nowrap">
                <img
                  src="../assets/images/logo-footer.png"
                  alt="Logo"
                  class="img-fluid me-3"
                />
                <p>Copyright 2020. All Rights Reserved</p>
              </div>
            </div>
          </div>
          <!-- Useful links -->
          <div class="col-3">
            <div id="useful-links">
              <ul class="d-flex justify-content-between">
                <li v-for="link in usefulLinks" :key="link">
                  <a :href="link.url">{{ link.text }}</a>
                </li>
              </ul>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  name: "Footer",
  data() {
    return {
      recentPostsFooter: [
        {
          img: require("../assets/images/our-office-4-square.jpg"),
          text: "lorem ipsum bla bla bla bla bla",
          date: "12:53 AM Dec 19th",
        },
        {
          img: require("../assets/images/our-office-5-square.jpg"),
          text: "lorem ipsum bla bla bla bla bla",
          date: "12:53 AM Dec 19th",
        },
      ],
      recentCommentsFooter: [
        {
          author: "John Doe",
          text: "lorem ipsum bla bla bla bla bla",
          date: "12:55 AM Dec 19th",
        },
        {
          author: "John Doe",
          text: "lorem ipsum bla bla bla bla bla",
          date: "12:55 AM Dec 19th",
        },
      ],
      categories: [
        "GADGETS",
        "PHOTOGRAPHY",
        "LIFESTYLE",
        "FASHION",
        "RECIPES",
        "TRAVEL",
        "BUSINESS",
        "ARCHITECTURE",
        "REVIEWS",
        "SPORTS",
        "VIDEOS",
        "TECHNOLOGY",
        "DESIGN",
      ],
      usefulLinks: [
        {
          text: "FAQ's",
          url: "#",
        },
        {
          text: "Sitemap",
          url: "#",
        },
        {
          text: "Contact Us",
          url: "#",
        },
      ],
    };
  },
};
</script>

<style lang="scss">
@import "@/assets/scss/_colors.scss";
#footer {
  color: $text-color-white;
}
#top-footer {
  background-color: $bg-color-black-gray;
  li {
    list-style-type: none;
    .badge {
      background-color: $bg-color-black;
    }
  }
}
#bottom-footer {
  background-color: $bg-color-night-gray;
  li {
    list-style-type: none;
  }
}
</style>