<template>
  <div id="app">
    <header-banner />

    <topic-banner 
      v-for="topic in topics" 
      v-bind:key="topic.id" 
      v-bind:bgColour="topic.bgColour" 
      v-bind:title="topic.title" 
      v-bind:titleColour="topic.titleColour"
      v-bind:imgName="topic.imgName"
      v-bind:flip="topic.flip"
      v-bind:blurb="topic.blurb"
    />
    <info-card v-if="selectedTopic" :topics="selectedTopic" />
  </div>
</template>

<script>
import HeaderBanner from './components/HeaderBanner.vue'
import TopicBanner from './components/TopicBanner.vue'
import InfoCard from './components/InfoCard'

import {eventBus} from './main.js'

export default {
  name: 'App',
  components: {
    'header-banner': HeaderBanner,
    'topic-banner': TopicBanner,
    'info-card': InfoCard
  },
  data: function() {
    return {
      topics: [
        {id: 1, bgColour: "#404040", title: "Dev.", titleColour: "#FABC2A", imgName: "terminals.png", flip: false, 
          blurb: "I have been developing software for  short period but problem solving has been a constant."},
        {id: 2, bgColour: "#72A276", title: "Photo.", titleColour: "#F15025", imgName: "camera.png", flip: true},
        {id: 3, bgColour: "#F15025", title: "Design.", titleColour: "#72A276", imgName: "design.png", flip: false},
        {id: 4, bgColour: "#404040", title: "Blog.", titleColour: "#72A276", imgName: "scroll.png", flip: true}
      ],
      selectedTopic = topic;
    }
  },
  mounted() {
    eventBus.$on('topic-selected', (topic) => {
      this.selectedTopic = beer;
      console.log(this.selectedTopic);
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
