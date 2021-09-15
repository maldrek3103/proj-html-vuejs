<template>
  <div id="posts">
    <!-- POST SECTION UNDER HEADER -->
    <section id="quick-preview">
      <!-- Suggested posts -->
      <section id="highlighted">
        <!-- Post cards -->
        <div v-for="(post, index) in highlighted" :key="index">
          <span>{{ post.category }}</span>
          <h4>{{ post.title }}</h4>
          <p>{{ post.description }}</p>
        </div>
      </section>
      <!-- Popular posts -->
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
      <!-- Recent posts -->
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
      <!-- Featured posts -->
      <section id="featured">
        <h4>FEATURED POSTS</h4>
        <div>
          <span>RECIPES</span>
          <h4>Tips to Help You Quickly Prepare your Lunch</h4>
          <p>bla bla bla bla bla bla bla</p>
        </div>
      </section>
      <!-- Featured author -->
      <section id="featured-author">
        <h4>FEATURED AUTHOR</h4>
        <div>
          <img src="../assets/images/avatar.jpg" alt="John Doe" />
          <h4>John Doe</h4>
          <p>
            Lorem, ipsum dolor sit amet consectetur adipisicing elit. Maxime,
            recusandae quos architecto hic beatae esse vel inventore corrupti
            sapiente repellat a numquam corporis illo doloribus nostrum culpa
            sit! Inventore, explicabo.
          </p>
        </div>
      </section>
    </section>
    <!-- MAIN POST SECTION WITH FILTER BAR -->
    <section id="main-preview">
      <!-- FILTER BAR -->
      <nav id="filter">
        <ul v-for="(category, index) in categories" :key="index">
          <li>
            {{ category }}
          </li>
        </ul>
      </nav>
      <!-- CARD POST FOR MAIN PREVIEW -->
      <div id="card-post" v-for="(post, index) in mainPosts" :key="index">
        <img :src="post.img" alt="" />
        <span id="publish-date">
          <h5>{{ post.date.day }}</h5>
          <h6>{{ post.date.month }}</h6>
        </span>
        <h2>{{ post.title }}</h2>
        <p>
          {{ post.description }}
        </p>
        <ul>
          <li>by {{ post.author }}</li>
          <li>{{ post.category }}</li>
          <li>{{ post.comments }}</li>
        </ul>
        <button>READ MORE</button>
      </div>
      <!-- PAGINATION -->
      <nav id="pagination">
        <ul class="pagination">
          <li>
            <a href="#">
              <span>&laquo;</span>
            </a>
          </li>
          <li><a href="#">1</a></li>
          <li><a href="#">2</a></li>
          <li><a href="#">3</a></li>
          <li>
            <a href="#">
              <span>&raquo;</span>
            </a>
          </li>
        </ul>
      </nav>
    </section>
    <!-- ASIDE SECTION FOR SOCIAL INTERACTION -->
    <section id="socials">
      <div><h4>LATEST FROM TWITTER</h4></div>
      <div><h4>PHOTOS FROM INSTAGRAM</h4></div>
      <div><h4>TAGS</h4></div>
      <div><h4>FIND US ON FACEBOOK</h4></div>
    </section>
  </div>
</template>

<script>
export default {
  name: "Main",
  data() {
    return {
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
      highlighted: [
        {
          category: "PHOTOGRAPY",
          title: "How To Take Better Concert Pictures in 30 Seconds",
          description: "bla bla bla bla bla bla bla bla bla",
        },
        {
          category: "GADGETS",
          title: "Gadget That Make Your Smartphone Even Smarter",
          description: "bla bla bla bla bla bla bla bla bla",
        },
        {
          category: "TRAVEL",
          title: "20 Top-Rated Tourist Attraction in Manhattan",
          description: "bla bla bla bla bla bla bla bla bla",
        },
        {
          category: "LIFESTYLE",
          title: "The Best Way to Ride a Motorcycle",
          description: "bla bla bla bla bla bla bla bla bla",
        },
        {
          category: "TRAVEL",
          title: "5 Fun Things to Do at the Beach",
          description: "bla bla bla bla bla bla bla bla bla",
        },
        {
          category: "RECIPES",
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
      mainPosts: [
        {
          img: [require("../assets/images/blog-54.jpg")],
          date: { day: "12", month: "JAN" },
          title: "How To Make Friends as a Grown-Up",
          description:
            "Lorem ipsum dolor sit amet consectetur, adipisicing elit. Autem ratione nobis quas illum, ea iure, veniam sed rerum obcaecati ex nemo deleniti quam nesciunt ad fugit accusamus aliquid? Quos, blanditiis?",

          author: "John Doe",
          category: ["Lifestyle", "Travel"],
          comments: "12 Comments",
        },
        {
          img: [require("../assets/images/blog-55 (1).jpg")],
          date: { day: "12", month: "JAN" },
          title: "Simple Way to Have a Pretty Face",
          description:
            "Lorem ipsum dolor sit amet consectetur, adipisicing elit. Autem ratione nobis quas illum, ea iure, veniam sed rerum obcaecati ex nemo deleniti quam nesciunt ad fugit accusamus aliquid? Quos, blanditiis?",
          author: "John Doe",
          category: ["Photography", "Travel"],
          comments: "12 Comments",
        },
        {
          img: [require("../assets/images/blog-56 (1).jpg")],
          date: { day: "12", month: "JAN" },
          title: "Ranking the greatest players in basketball",
          description:
            "Lorem ipsum dolor sit amet consectetur, adipisicing elit. Autem ratione nobis quas illum, ea iure, veniam sed rerum obcaecati ex nemo deleniti quam nesciunt ad fugit accusamus aliquid? Quos, blanditiis?",
          author: "John Doe",
          category: ["Sport", "Business"],
          comments: "12 Comments",
        },
        {
          img: [require("../assets/images/blog-58 (1).jpg")],
          date: { day: "12", month: "JAN" },
          title: "Top Camper Trailer Towing Tips",
          description:
            "Lorem ipsum dolor sit amet consectetur, adipisicing elit. Autem ratione nobis quas illum, ea iure, veniam sed rerum obcaecati ex nemo deleniti quam nesciunt ad fugit accusamus aliquid? Quos, blanditiis?",
          author: "John Doe",
          category: ["Travel", "Lifestyle"],
          comments: "12 Comments",
        },
        {
          img: [
            require("../assets/images/blog-13.jpg"),
            require("../assets/images/blog-16.jpg"),
            require("../assets/images/blog-20.jpg"),
            require("../assets/images/blog-23.jpg"),
            require("../assets/images/blog-29.jpg"),
            require("../assets/images/blog-40.jpg"),
          ],
          date: { day: "8", month: "JAN" },
          title: "10 Best Travel Tips After 5 Years Traveling The World",
          description:
            "Lorem ipsum dolor sit amet consectetur, adipisicing elit. Autem ratione nobis quas illum, ea iure, veniam sed rerum obcaecati ex nemo deleniti quam nesciunt ad fugit accusamus aliquid? Quos, blanditiis?",
          author: "John Doe",
          category: ["Travel", "Lifestyle"],
          comments: "12 Comments",
        },
      ],
    };
  },
};
</script>

<style>
</style>