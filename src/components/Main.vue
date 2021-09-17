<template>
  <div id="posts">
    <!-- POST SECTION UNDER HEADER -->
    <section id="quick-preview">
      <!-- Suggested posts -->
      <section id="highlighted">
        <div class="container py-5">
          <!-- Post cards -->
          <div class="row">
            <div
              v-for="(post, index) in highlighted"
              :key="index"
              class="col-4 p-0"
            >
              <div
                class="image m-3"
                @mouseover="mouseOver"
                @mouseleave="mouseOver"
              >
                <img :src="post.img" class="img-fluid" />
                <div class="text">
                  <span class="badge badge-secondary">{{ post.category }}</span>
                  <h4>{{ post.title }}</h4>
                  <p v-show="active">{{ post.description }}</p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>
      <div class="container py-5">
        <div class="row">
          <!-- Popular posts -->
          <section id="populars" class="col-4">
            <h4>POPULAR POSTS</h4>
            <ul class="list-group list-group-flush">
              <li
                v-for="(post, index) in popularPosts"
                :key="index"
                class="list-group-item py-3 ps-0"
              >
                <div class="row">
                  <div class="col-2">
                    <img :src="post.img" :alt="post.title" class="img-fluid" />
                  </div>
                  <div class="col-10">
                    <h6 class="m-0">{{ post.title }}</h6>
                    <p class="m-0">{{ post.date }}</p>
                  </div>
                </div>
              </li>
            </ul>
          </section>
          <!-- Recent posts -->
          <section id="recents" class="col-4">
            <h4>RECENT POSTS</h4>
            <ul class="list-group list-group-flush">
              <li
                v-for="(post, index) in recentPosts"
                :key="index"
                class="list-group-item py-3 ps-0"
              >
                <div class="row">
                  <div class="col-2">
                    <img :src="post.img" :alt="post.title" class="img-fluid" />
                  </div>
                  <div class="col-10">
                    <h6 class="m-0">{{ post.title }}</h6>
                    <p class="m-0">{{ post.date }}</p>
                  </div>
                </div>
              </li>
            </ul>
          </section>
          <section id="featured" class="col-4">
            <!-- Featured posts -->
            <section id="featured-posts">
              <h4>FEATURED POSTS</h4>
              <div>
                <img src="../assets/images/blog-66.jpg" class="img-fluid" />
                <span class="badge badge-secondary">RECIPES</span>
                <h3>Tips to Help You Quickly Prepare your Lunch</h3>
                <p>bla bla bla bla bla bla bla</p>
              </div>
            </section>
            <!-- Featured author -->
            <section id="featured-author">
              <h4>FEATURED AUTHOR</h4>
              <div>
                <div class="row">
                  <div class="col-4">
                    <img
                      src="../assets/images/avatar.jpg"
                      alt="John Doe"
                      class="img-fluid"
                    />
                  </div>
                  <div class="col-8">
                    <h6>John Doe</h6>
                    <p>
                      Lorem, ipsum dolor sit amet consectetur adipisicing elit.
                      Maxime, recusandae quos architecto hic beatae esse vel
                      inventore corrupti sapiente repellat a numquam corporis.
                    </p>
                  </div>
                </div>
              </div>
            </section>
          </section>
        </div>
      </div>
    </section>

    <!-- MAIN POST SECTION WITH FILTER BAR -->
    <section id="main-preview">
      <!-- FILTER BAR -->
      <nav id="filter">
        <div class="container">
          <div class="d-flex justify-content-between align-items-center">
            <i class="fas fa-chevron-left"></i>
            <ul class="d-flex justify-content-between m-0 py-5">
              <li
                v-for="(category, index) in categories"
                :key="index"
                class="py-2 px-5 bg-dark overflow-hidden text-white"
              >
                {{ category }}
              </li>
            </ul>
            <i class="fas fa-chevron-right"></i>
          </div>
        </div>
      </nav>
      <!-- CARD POST FOR MAIN PREVIEW -->
      <div class="container py-5">
        <div class="row">
          <div class="col-9">
            <div id="card-post" v-for="(post, index) in mainPosts" :key="index">
              <div id="card-image">
                <img :src="post.img" alt="" class="img-fluid" />
              </div>
              <div class="d-flex py-3">
                <div id="publish-date">
                  <h5>{{ post.date.day }}</h5>
                  <h6>{{ post.date.month }}</h6>
                </div>
                <div id="card-text" class="ms-3">
                  <h2>{{ post.title }}</h2>
                  <p class="py-3">
                    {{ post.description }}
                  </p>
                  <div class="d-flex justify-content-between">
                    <ul class="d-flex">
                      <li>by {{ post.author }}</li>
                      <li>{{ post.category }}</li>
                      <li>{{ post.comments }}</li>
                    </ul>
                    <button>READ MORE</button>
                  </div>
                </div>
              </div>
              <hr />
            </div>
            <!-- PAGINATION -->
            <div>
              <nav class="d-flex justify-content-end">
                <ul class="pagination">
                  <li class="page-item">
                    <a href="#" class="page-link">
                      <span>&laquo;</span>
                    </a>
                  </li>
                  <li class="page-item"><a href="#" class="page-link">1</a></li>
                  <li class="page-item"><a href="#" class="page-link">2</a></li>
                  <li class="page-item"><a href="#" class="page-link">3</a></li>
                  <li class="page-item">
                    <a href="#" class="page-link">
                      <span>&raquo;</span>
                    </a>
                  </li>
                </ul>
              </nav>
            </div>
          </div>
          <!-- ASIDE SECTION FOR SOCIAL INTERACTION -->
          <div class="col-3">
            <section id="socials">
              <div><h4>LATEST FROM TWITTER</h4></div>
              <div><h4>PHOTOS FROM INSTAGRAM</h4></div>
              <div><h4>TAGS</h4></div>
              <div><h4>FIND US ON FACEBOOK</h4></div>
            </section>
          </div>
        </div>
      </div>
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
        // "BUSINESS",
        // "ARCHITECTURE",
        // "REVIEWS",
        // "SPORTS",
        // "VIDEOS",
        // "TECHNOLOGY",
        // "DESIGN",
      ],
      highlighted: [
        {
          category: "PHOTOGRAPY",
          title: "How To Take Better Concert Pictures in 30 Seconds",
          description: "bla bla bla bla bla bla bla bla bla",
          img: require("../assets/images/blog-46.jpg"),
        },
        {
          category: "GADGETS",
          title: "Gadget That Make Your Smartphone Even Smarter",
          description: "bla bla bla bla bla bla bla bla bla",
          img: require("../assets/images/blog-47.jpg"),
        },
        {
          category: "TRAVEL",
          title: "20 Top-Rated Tourist Attraction in Manhattan",
          description: "bla bla bla bla bla bla bla bla bla",
          img: require("../assets/images/blog-48.jpg"),
        },
        {
          category: "LIFESTYLE",
          title: "The Best Way to Ride a Motorcycle",
          description: "bla bla bla bla bla bla bla bla bla",
          img: require("../assets/images/blog-49.jpg"),
        },
        {
          category: "TRAVEL",
          title: "5 Fun Things to Do at the Beach",
          description: "bla bla bla bla bla bla bla bla bla",
          img: require("../assets/images/blog-50.jpg"),
        },
        {
          category: "RECIPES",
          title: "Amazingly Fresh Fruit And Herb Drinks For Summer",
          description: "bla bla bla bla bla bla bla bla bla",
          img: require("../assets/images/blog-51.jpg"),
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
            // require("../assets/images/blog-16.jpg"),
            // require("../assets/images/blog-20.jpg"),
            // require("../assets/images/blog-23.jpg"),
            // require("../assets/images/blog-29.jpg"),
            // require("../assets/images/blog-40.jpg"),
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
      active: false,
    };
  },
  methods: {
    mouseOver() {
      this.active = !this.active;
    },
  },
};
</script>

<style lang="scss">
@import "@/assets/scss/_colors.scss";
#highlighted {
  background-color: $bg-color-light-grey;
  .image {
    position: relative;
    img {
      filter: brightness(50%);
    }
    .text {
      position: absolute;
      bottom: 0;
      left: 1rem;
      color: $text-color-white;
    }
  }
}
.badge {
  background-color: $bg-color-primary;
}
#populars,
#recents,
#featured,
#featured-author {
  h4 {
    font-weight: bold;
  }
  p {
    font-size: 0.8rem;
    color: $text-color-grey-2;
  }
}
#filter {
  background-color: $bg-color-primary;
}
#card-text {
  li {
    list-style-type: none;
  }
}
#card-post {
  button {
    background-color: $bg-color-white;
    border: 1px solid $border-color-gray-6;
    border-radius: 10px;
    padding: 0 1rem;
  }
}
</style>