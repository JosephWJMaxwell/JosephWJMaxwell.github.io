<template>
  <div class="home background-image" id="Home">
    <v-parallax
      height="950"
      :src="selectedHomeImage"
      id="home-image"
    >
      <v-layout fill-height align-center>
          <v-container>
            <v-row align="center" justify="center" class="white--text">
              <v-col cols="12">
                <div :class="{'display-4 font-weight-bold ': $vuetify.breakpoint.smAndUp, 'display-2 font-weight-bold': $vuetify.breakpoint.smAndDown}">
                  LiQuid Gaming
                </div>
                <div :class="{'subtitle-1': $vuetify.breakpoint.smAndDown}" class="home-text">
                  We are a high-level clan in various gaming platforms with a community of over 2000 players. <br/>
                  We currently host two servers in Squad and have plan for more in the future. <br/>
                  <br/>
                  We are eager to help new or returning players rediscover their passion for gaming. <br/>
                  Please scroll down and take a look, we would love for you to join us! <br/>
                </div>
              </v-col>
            </v-row>
          </v-container>
        </v-layout>
    </v-parallax>
    <v-container class="mt-5 dark black--background component-container" id="About">        
      <v-card :elevation="5" class="home-cards">
        <About :discord="dicord" :teamMembers="teamMembers"/>
      </v-card>
    </v-container>
  </div>
</template>

<script>
// @ is an alias to /src
import About from "@/components/About.vue"
//Json files
import mediaLinks from "@/assets/json/mediaLinks.json"

export default {
  name: "home",
  components: {
    About
  },
  data() {
    return {
      mediaLinks: mediaLinks
    };
  },
  methods: {
    randomItem (items) {
      return items[Math.floor(Math.random()*items.length)];
    },
    fileNamesGetter(fileNames){   
      let homePageImage = [];
      let homePageImageJson = [];
      fileNames.keys().forEach(key => (homePageImage.push(fileNames(key))));
      homePageImage.forEach(image => {
        const addImage = {
          src: image
        }
        homePageImageJson.push(addImage)
      });
      return homePageImageJson;
    }
  },
  mounted() {
    
  },
  created() {
    let homeImageFolder = require.context('../assets/HomePageImages/', true);
    const homeImageFiles = this.fileNamesGetter(homeImageFolder);
    this.selectedHomeImage = this.randomItem(homeImageFiles).src;
  }
};
</script>

<style lang="css">
  #home-image .v-parallax__content {
    background: linear-gradient(45deg, rgba(100,100,100,.33), rgba(100,100,100,.7));
  }
  .background-image{
    background-image: url('~@/assets/escheresque_ste.png');
    background-repeat: repeat;
  }
  .home-cards{
    background:#222222 !important;
    padding:30px !important;
    border-radius: 10px !important;
  }
  .home-text{
    opacity: 0.75 !important; 
    margin-top:10px !important;
  }
</style>
