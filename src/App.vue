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
      topics: null
    }
  },
  mounted() {
    fetch('')
    .then(res => res.json())
    .then(payload => {this.topics = payload})



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
.grid-container {
    display: flex;
    justify-content: space-around;
    flex-wrap: wrap;
    max-width: 100vw;
    height: auto;
    padding: 2%;
}
</style>
