<template>
  <div> <nav class="navContainer"> 

    <div class="navItemList">
    <a href="#Home" @click="clicked('Home')">Home</a><a href="#About" @click="clicked('About')">About</a><a href="#News" @click="clicked('News')">News</a></div>
  </nav>

  <video
  className="fullscreen-video"
  id="myVideo"
  autoPlay="autoPlay"
  muted
  loop
>
  <source src="http://commondatastorage.googleapis.com/gtv-videos-bucket/sample/ElephantsDream.mp4" />
  Your browser does not support the video tag.
</video>

  <div class="sidenav">
    <a href="#">Music</a>
    <a href="#">JavaScript</a>
    <a href="#">The Trio</a>
    <a href="#">Contact</a>
  </div>

  <div class="bottomSidenav">
    <a href="#">github</a>
    <a href="#">linkedIn</a>
    <a href="#">Facebook</a>
    <a href="#">Instagram</a>
  </div>

  <h2 style="position: fixed; top: 9%; padding: 2%;z-index: 2000000; text-align: center;left: 50%; transform: translate(-50%, -50%); ">Leif Christian</h2> <br>
  <div v-if="Home">  <HomeView></HomeView> </div>
    <div v-if="About">  <AboutView></AboutView></div>
      <div v-if="News">  <NewsView></NewsView></div>
  </div>
  
</template>

  <script>
  import { loremIpsum } from "lorem-ipsum";
  import HomeView from "./views/HomeView.vue"
  import AboutView from "./views/AboutView.vue"
  import NewsView from "./views/NewsView.vue"
  import './Extra.css';

  export default {
    name: "App",
    components: {
    HomeView, NewsView, AboutView},

    data: function () {

      return {
      Home: true,
      About: false,
      News: false
          }

    },
  
    computed: {
      text() {
     return null
      },
  
      transitions() {
      return null
      },

    },
  
    methods: {

      clicked(e){

        switch(e){
          case "Home":
            this.Home = true;
            this.About = false;
            this.News = false; 
          break;
          case "About":
            this.About = true;
            this.Home = false;
            this.News = false; 
          break;
          case "News":
          this.News = true; 
          this.Home = false;
          this.About = false;
          break
          default:
            return;
        }
        
      },

      loremIpsum() {
        return loremIpsum({
          units: "sentences",
          count: 10,
        });
      },

    },
  };
  </script>
  
  <style>

  body {background: black; color: white}
  #app2 {
    max-width: 800px;
    margin:  auto;
  }
  
  p {
    text-align: center;
    line-height: 150%;
  }

  .vue-flux * {
  border-radius: 2em;
 /* border-radius: 2rem;	box-shadow: 0 0 12px 0px rgba(29, 114, 198, 0.85);  */
	}

  .vue-flux {
    border-radius: 2em;
    box-shadow: 0 0 12px 0px rgba(29, 114, 198, 0.85); 
  }

  .navContainer { opacity: 0.6;
    position: fixed; top: 6%; width: 80%; background: black; border-radius: 2rem; color: white; font-weight: 900;
    left: 50%; transform: translate(-50%, -50%); z-index: 200000;
    opacity: 0.8=9;
  }

  .navContainer a:hover {color: magenta;}

  .navItemList { font-size: 1.4rem; opacity: 1;
    flex-wrap: wrap; display: flex; flex-direction: row; padding: 8px;list-style: none;  text-align: center; margin: auto; gap: 20px;justify-content: center;
  }

  /* side nav below ---------- */

  a:link { text-decoration: none; }

a:visited { text-decoration: none; color: inherit}

a:hover { text-decoration: none; }

a:active { text-decoration: none; }

  .sidenav {
    height: 25%; /* Full-height: remove this if you want "auto" height */
    width: 9%; /* Set the width of the sidebar */
    position: fixed; /* Fixed Sidebar (stay in place on scroll) */
    z-index: 1; /* Stay on top */
    top: 0; /* Stay at the top */
    left: 0;
    background-color: black; /* Black */
    overflow-x: hidden; /* Disable horizontal scroll */
    padding-top: 20px;
  }
  
  /* The navigation menu links */
  .sidenav a {
    padding: 6px 8px 6px 16px;
    text-decoration: none;
    font-size: 25px;
    color: white;
    display: block;
  }
  
  /* When you mouse over the navigation links, change their color */
  .sidenav a:hover {
    color: magenta
  }
  
  /* Style page content */
  .main {
    margin-left: 160px; /* Same as the width of the sidebar */
    padding: 0px 10px;
  }
  
  /* On smaller screens, where height is less than 450px, change the style of the sidebar (less padding and a smaller font size) */
  @media screen and (max-height: 450px) {
    .sidenav {padding-top: 15px;}
    .sidenav a {font-size: 18px;}
  }


  .bottomSidenav {
    height: 100%; /* Full-height: remove this if you want "auto" height */
    width: 9%; /* Set the width of the sidebar */
    position: fixed; /* Fixed Sidebar (stay in place on scroll) */
    z-index: 1; /* Stay on top */
    top: 70%; /* Stay at the top */
    left: 91%;
    background-color: black; /* Black */
    overflow-x: hidden; /* Disable horizontal scroll */
    padding-top: 20px;
  }
  
  /* The navigation menu links */
  .bottomSidenav a {
    padding: 6px 8px 6px 16px;
    text-decoration: none;
    font-size: 25px;
    color: white;
    display: block;
  }
  
  /* When you mouse over the navigation links, change their color */
  .bottomSidenav a:hover {
    color: magenta;
  }

  </style>