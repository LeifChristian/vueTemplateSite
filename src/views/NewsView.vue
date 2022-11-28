<template>
    <div style="margin-top: 2%;" id="app2">
      <!-- <p>{{ text[0] }}</p> -->
     
    <br><br>
    <br class="">
    <div style="" id="id1">
      <vue-flux :options="options" :images="images" :transitions="transitions">
        <template v-slot:preloader>
          <flux-preloader />
        </template>
  
        <template v-slot:caption>
          <flux-caption />
        </template>
 
        <!-- <template v-slot:controls>
          <flux-controls />
        </template> -->
  
        <template v-slot:pagination>
          <flux-pagination />
        </template>
  
        <template v-slot:index>
          <flux-index />
        </template>
      </vue-flux> </div>
      <h1>NEWS</h1>
      <h1>NEWS</h1>
      <h1>NEWS</h1>
      <p>{{ text[1] }}</p>
      <p>{{ text[1] }}</p>
      <p>{{ text[1] }}</p>
      <p>{{ text[1] }}</p>

    </div>

  </template>
  
  <script>
  import {
    VueFlux,
    FluxCaption,
    // FluxControls,
    FluxIndex,
    FluxPagination,
    FluxPreloader,
  } from "vue-flux";
  import { loremIpsum } from "lorem-ipsum";
  
  export default {
    
    name: "HomeView",
    components: {
      VueFlux,
      FluxCaption,
      // FluxControls,
      FluxIndex,
      FluxPagination,
      FluxPreloader,
    },
  
    computed: {
      text() {
        return [this.loremIpsum(), this.loremIpsum(), this.loremIpsum()];
      },

      options() {
        return {
          autoplay: true,
          autohideTime: 3000,
        };
      },
  
      transitions() {
        return ["cube"];
        // 'fade', 'kenburn',
				// 'swipe', 'slide',
				// 'waterfall', 'zip', 'blinds2d',
				// 'blocks1', 'blocks2',
				// 'concentric', 'warp', 'camera',
				// 'cube', 'book', 'fall',
				// 'wave', 'blinds3d',
				// 'round1', 'round2', 'explode',
      },
  
      images() {
        return [...Array(7).keys()].map(
          (i) => `https://picsum.photos/800/600?random=${i}`
        );
      },
    },
  
    methods: {
  
      clicked(e){alert(e)},

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



  </style>