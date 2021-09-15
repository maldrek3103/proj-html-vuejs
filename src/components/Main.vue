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
      <ul v-for="(post, index) in popularPosts" :key="index">
        <li>
          <img :src="post.img" :alt="post.title" />
          <h5>{{ post.title }}</h5>
          <p>{{ post.date }}</p>
        </li>
      </ul>
    </section>
    <section id="recents"></section>
    <section id="featured"></section>
    <section id="featured-author"></section>
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
    };
  },
};
</script>

<style>
</style>