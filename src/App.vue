<template>
  <div id="app">
    <header-banner />

    <topic-list :topics="topics"/>
    <info-card v-if="selectedTopic" :topic="selectedTopic" />
  </div>
</template>

<script>
import HeaderBanner from './components/HeaderBanner.vue'
import TopicList from './components/TopicList.vue'
import InfoCard from './components/InfoCard'

import {eventBus} from './main.js'

export default {
  name: 'App',
  components: {
    'header-banner': HeaderBanner,
    'topic-list': TopicList,
    'info-card': InfoCard
  },
  data: function() {
    return {
      topics: [
        {id: 1, bgColour: "#404040", title: "Dev.", titleColour: "#FABC2A", imgName: "terminals.png", flip: false, 
          blurb: "I have been developing software for short period but problem solving has been a constant."},
        {id: 2, bgColour: "#72A276", title: "Photo.", titleColour: "#F15025", imgName: "camera.png", flip: true},
        {id: 3, bgColour: "#F15025", title: "Design.", titleColour: "#72A276", imgName: "design.png", flip: false},
        {id: 4, bgColour: "#404040", title: "Blog.", titleColour: "#72A276", imgName: "scroll.png", flip: true}
      ],
      selectedTopic: null
    }
  },
  mounted() {
    eventBus.$on('topic-selected', (topic) => {
      this.selectedTopic = topic;
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
