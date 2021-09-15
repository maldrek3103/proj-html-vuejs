<template>
  <div id="footer">
    <section id="top-footer">
      <span>Get in Touch</span>
      <!-- About the blog -->
      <div>
        <h5>ABOUT THE BLOG</h5>
        <p>
          Lorem ipsum dolor sit amet, consectetur adipisicing elit. Officiis
          consequatur nulla eveniet possimus hic nihil, aliquid earum
          exercitationem corporis ipsam, assumenda modi quia? Voluptas ipsa
          nesciunt magni voluptatum minima saepe.
        </p>
      </div>
      <!-- Recent posts -->
      <div>
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
      <div>
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
      <div>
        <h5>CATEGORIES</h5>
        <ul v-for="category in categories" :key="category">
          <li>{{ category }}</li>
        </ul>
      </div>
    </section>
    <section id="bottom-footer">
      <!-- LOGO + Copyright -->
      <div id="copyright">
        <img src="../assets/images/logo-footer.png" alt="Logo" />
        <h6>Copyright 2020. All Rights Reserved</h6>
      </div>
      <!-- Useful links -->
      <div id="useful-links">
        <ul v-for="link in usefulLinks" :key="link">
          <li>
            <a :href="link.url">{{ link.text }}</a>
          </li>
        </ul>
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

<style>
</style>