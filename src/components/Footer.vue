<template>
  <div id="footer">
    <section id="top-footer" class="py-5">
      <div class="container">
        <div class="row">
          <span>Get in Touch</span>
          <!-- About the blog -->
          <div id="about" class="col-3">
            <h5>ABOUT THE BLOG</h5>
            <p>
              Lorem ipsum dolor sit amet, consectetur adipisicing elit. Officiis
              consequatur nulla eveniet possimus hic nihil, aliquid earum
              exercitationem corporis ipsam, assumenda modi quia? Voluptas ipsa
              nesciunt magni voluptatum minima saepe.
            </p>
            <a href="#">View more <i class="fas fa-chevron-right"></i></a>
          </div>
          <!-- Recent posts -->
          <div id="posts" class="col-3">
            <h5>RECENT POSTS</h5>
            <ul>
              <li
                v-for="(post, index) in recentPostsFooter"
                :key="index"
                class="d-flex"
              >
                <img :src="post.img" alt="Our office" />
                <div>
                  <h6>{{ post.text }}</h6>
                  <p>{{ post.date }}</p>
                </div>
              </li>
            </ul>
          </div>
          <!-- Recent comments -->
          <div id="comments" class="col-3">
            <h5>RECENT COMMENTS</h5>
            <ul>
              <li v-for="(comment, index) in recentCommentsFooter" :key="index">
                <h6>
                  {{ comment.author }} commented on
                  <a href="#">{{ comment.text }}</a>
                </h6>
                <p>{{ comment.date }}</p>
              </li>
            </ul>
          </div>
          <!-- Categories -->
          <div id="categories" class="col-3">
            <h5>CATEGORIES</h5>
            <ul>
              <li v-for="(category, index) in categories" :key="index">
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
                <li v-for="(link, index) in usefulLinks" :key="index">
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

  #posts {
    img {
      border-radius: 50%;
    }
  }
  ul {
    padding-left: 0;

    li {
      list-style-type: none;
      .badge {
        background-color: $bg-color-black;
      }
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