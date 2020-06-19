<template>
  <div id="app">

    <header-banner />
   
    <topic-list :topics="topics"/>
  
  </div>
</template>

<script>
import HeaderBanner from './components/HeaderBanner.vue'
import TopicList from './components/TopicList.vue'

import {eventBus} from './main.js'

export default {
  name: 'App',
  components: {
    'header-banner': HeaderBanner,
    'topic-list': TopicList,
  },
  data: function() {
    return {
      topics: [
        {
          id: 1, 
          bgColour: "#404040", 
          title: "Dev.", 
          titleColour: "#FABC2A", 
          imgName: "terminals.png", 
          flip: false, 
          blurb: "I have been developing software for short period but problem solving has been a constant.",
          infoCard: null,
          portfolio: [
            {
              title: "LukeMelvin.com",
              blurb: "This was a scratch built in house project for our own portfolio site. It is always changing.",
              image: 'lukemelvin.png',
              link: 'http://www.lukemelvin.com'
            },
            {
              title: "Punk API",
              blurb: "A small vue application to try out the BrewDog Punk api.",
              image: null,
              link: 'https://github.com/LUKERHYS/Brewdog-Punk-API'
            },
            {
              title: "Simulated Network Monitor",
              blurb: "This python backend simulates live network traffic. We decided to build this so that one could use it to design and develop a network monitoring dash board offline. We also built a React front end for it.",
              image: null,
              link: 'https://github.com/LUKERHYS/Simulated-Network-Monitor'
            },
            {
              title: "Stocks & Shares Portfolio",
              blurb: "This project was a vue based, web application that holds and tracks personal stocks and shares fed from several APIs.",
              image: null,
              link: 'https://github.com/LUKERHYS/Stocks-Shares-portfolio-VueJS-MongoDB-Express'
            },
            {
              title: "Gym Booking system",
              blurb: "This project is a full CRUD Ruby and Sinatra web application. It can track members, workouts and their interactions.",
              image: null,
              link: 'https://github.com/LUKERHYS/Gym-Booking-App-Ruby-HTML-CSS'
            }
          ]
        },
        {
          id: 2, 
          bgColour: "#72A276",
          title: "Photo.", 
          titleColour: "#F15025", 
          imgName: "camera.png", 
          flip: true, blurb: "Photographys is ace!", 
          infoCard: null,
          portfolio: [
            {
              title: "LukeRhysPhotography",
              blurb: "LukeRhysPhotography started life as an independant entity run by myself as a freelancer. Once the decision was made to start the agency it was an easy desicion to bring it in house.",
              image: 'LRP.png',
              link: 'https://www.lukerhysphotography.com/'
            }
          ]
        },
        {
          id: 3, 
          bgColour: "#F15025", 
          title: "Design.", 
          titleColour: "#72A276", 
          imgName: "design.png", 
          flip: false, 
          blurb: "Design is tough but I enjoy it", 
          infoCard: null,
          portfolio: [
            {
              title: "golfclubs4cash. ltd",
              blurb: "GC4C were one of the very first design clients we took on and we continue to do all sorts of work for them. they keep things interesting.",
              image: 'icon-img-placeholder.svg',
              link: null
            }
          ]
        },
        {
          id: 4, 
          bgColour: "#404040", 
          title: "Blog.", 
          titleColour: "#72A276", 
          imgName: "scroll.png", 
          flip: true, 
          blurb: "Blog you say", 
          infoCard: null,
          portfolio: [],
          posts: []
        }
      ]
    }
  },
  mounted() {
      eventBus.$on('topic-selected', (infoCardDetails) => {
        let foundIndex = this.topics.findIndex(currentId => currentId.id == infoCardDetails.id);
        this.topics[foundIndex]['infoCard'] = infoCardDetails;
    })
  }
}
</script>

<style>
#app {
  font-family: Futura, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
