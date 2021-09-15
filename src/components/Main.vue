<template>
  <!-- POST SECTION UNDER HEADER -->
  <div id="highlighted-posts">
    <!-- Suggested posts -->
    <section id="suggested">
      <!-- Post cards -->
      <div v-for="(post, index) in highlightedPosts" :key="index">
        <span>{{ post.label }}</span>
        <h4>{{ post.title }}</h4>
        <p>{{ post.description }}</p>
      </div>
    </section>
    <section id="populars">
      <h4>POPULAR POSTS</h4>
      <ul v-for="(post, index) in popularPosts" :key="index">
        <li>
          <img :src="post.img" :alt="post.title" />
          <h5>{{ post.title }}</h5>
          <p>{{ post.date }}</p>
        </li>
      </ul>
    </section>
    <section id="recents">
      <h4>RECENT POSTS</h4>
      <ul v-for="(post, index) in recentPosts" :key="index">
        <li>
          <img :src="post.img" :alt="post.title" />
          <h5>{{ post.title }}</h5>
          <p>{{ post.date }}</p>
        </li>
      </ul>
    </section>
    <section id="featured">
      <h4>FEATURED POSTS</h4>
      <div>
        <span>RECIPES</span>
        <h4>Tips to Help You Quickly Prepare your Lunch</h4>
        <p>bla bla bla bla bla bla bla</p>
      </div>
    </section>
    <section id="featured-author">
      <h4>FEATURED AUTHOR</h4>
      <div>
        <img src="../assets/images/avatar.jpg" alt="John Doe" />
        <h4>John Doe</h4>
        <p>
          Lorem, ipsum dolor sit amet consectetur adipisicing elit. Maxime,
          recusandae quos architecto hic beatae esse vel inventore corrupti
          sapiente repellat a numquam corporis illo doloribus nostrum culpa sit!
          Inventore, explicabo.
        </p>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  name: "Main",
  data() {
    return {
      highlightedPosts: [
        {
          label: "PHOTOGRAPY",
          title: "How To Take Better Concert Pictures in 30 Seconds",
          description: "bla bla bla bla bla bla bla bla bla",
        },
        {
          label: "GADGETS",
          title: "Gadget That Make Your Smartphone Even Smarter",
          description: "bla bla bla bla bla bla bla bla bla",
        },
        {
          label: "TRAVEL",
          title: "20 Top-Rated Tourist Attraction in Manhattan",
          description: "bla bla bla bla bla bla bla bla bla",
        },
        {
          label: "LIFESTYLE",
          title: "The Best Way to Ride a Motorcycle",
          description: "bla bla bla bla bla bla bla bla bla",
        },
        {
          label: "TRAVEL",
          title: "5 Fun Things to Do at the Beach",
          description: "bla bla bla bla bla bla bla bla bla",
        },
        {
          label: "RECIPES",
          title: "Amazingly Fresh Fruit And Herb Drinks For Summer",
          description: "bla bla bla bla bla bla bla bla bla",
        },
      ],
      popularPosts: [
        {
          img: require("../assets/images/blog-55.jpg"),
          title: "Simple Ways to Have a Pretty Face",
          date: "January 12, 2019",
        },
        {
          img: require("../assets/images/blog-56.jpg"),
          title: "Ranking the greatest players in basketball",
          date: "January 12, 2019",
        },
        {
          img: require("../assets/images/blog-57.jpg"),
          title: "4 Ways to Look Cool in Glasses",
          date: "January 12, 2019",
        },
        {
          img: require("../assets/images/blog-58.jpg"),
          title: "Top Campers Trailer Towing Tips",
          date: "January 12, 2019",
        },
        {
          img: require("../assets/images/blog-59.jpg"),
          title: "5 Lovely Walks in New York",
          date: "January 12, 2019",
        },
      ],
      recentPosts: [
        {
          img: require("../assets/images/blog-65.jpg"),
          title: "Main Reasons To Stop Texting And Driving",
          date: "January 12, 2019",
        },
        {
          img: require("../assets/images/blog-66 (1).jpg"),
          title: "Tips to Help You Quickly Prepare your Lunch",
          date: "January 12, 2019",
        },
        {
          img: require("../assets/images/blog-67.jpg"),
          title: "Why should i buy a smartwatch?",
          date: "January 12, 2019",
        },
        {
          img: require("../assets/images/blog-68.jpg"),
          title: "The best augmented reality smartglasses",
          date: "January 12, 2019",
        },
        {
          img: require("../assets/images/blog-69.jpg"),
          title: "12 Healthiest Foods to Eat for Breakfast",
          date: "January 12, 2019",
        },
      ],
    };
  },
};
</script>

<style>
</style>