<template>
  <div id="app">

    <header-banner />
   
    <topic-list :topics="topics"/>
    <!-- <info-card v-if="!isHidden" transition="expand" :details="this.infoCard" id="info" /> -->

    <!-- <full-footer /> -->
  </div>
</template>

<script>
import HeaderBanner from './components/HeaderBanner.vue'
import TopicList from './components/TopicList.vue'
// import InfoCard from './components/InfoCard.vue'
import FullFooter from './components/Footer.vue'


import {eventBus} from './main.js'

export default {
  name: 'App',
  components: {
    'header-banner': HeaderBanner,
    'topic-list': TopicList,
    // 'info-card' : InfoCard,
    'full-footer' : FullFooter
  },
  data: function() {
    return {
      topics: null,
      infoCard: null,
      isHidden: true
    }
  },
  mounted() {
    fetch('https://cms.lukemelvin.com/topics')
    .then(res => res.json())
    .then(payload => {this.topics = payload})



      eventBus.$on('topic-selected', (infoCardDetails) => {
        let foundIndex = this.topics.findIndex(currentId => currentId.id == infoCardDetails.id);
        this.topics[foundIndex]['infoCard'] = infoCardDetails;
        // this.infoCard= infoCardDetails;
      })
      eventBus.$on ('hidden-state', (stateChange) => {
        this.isHidden = stateChange;
      })
  }
}
</script>

<style>
#app {
  font-family: Arial, sans-serif;
  /* font: 2.5vh  Helvetica, sans-serif; */
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

</style>
