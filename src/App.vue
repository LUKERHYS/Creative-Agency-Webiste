<template>
  <div id="app">
    <header-banner />
  <div class="grid-container">
      <topic-banner 
        v-for="topic in topics" 
        v-bind:key="topic.id" 
        v-bind:bgColour="topic.bgColour" 
        v-bind:title="topic.title" 
        v-bind:titleColour="topic.titleColour"
        v-bind:imgName="topic.imgName"
        v-bind:flip="topic.flip"
      />
      </div>
  </div>
</template>

<script>
import HeaderBanner from './components/HeaderBanner.vue'
import TopicBanner from './components/TopicBanner.vue'

export default {
  name: 'App',
  components: {
    'header-banner': HeaderBanner,
    'topic-banner': TopicBanner
  },
  data: function() {
    return {
      topics: [
        {id: 1, bgColour: "#404040", title: "Dev.", titleColour: "#FABC2A", imgName: "terminals.png", flip: false},
        {id: 2, bgColour: "#72A276", title: "Photo.", titleColour: "#F15025", imgName: "camera.png", flip: true},
        {id: 3, bgColour: "#F15025", title: "Design.", titleColour: "#72A276", imgName: "design.png", flip: false},
        {id: 4, bgColour: "#404040", title: "Blog.", titleColour: "#72A276", imgName: "scroll.png", flip: true}
      ]
    }
  }
}
</script>

<style>
#app {
  font-family: Futura, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
div {
    border: red solid;
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
