<template>
    <div v-on:click="[handleClick()]" :style="[this.divStyle, this.icon_heading_flip]" :topic="topic" class="main">

        <div class="img-container">
            <img :src="require(`@/assets/icons/${topic.imgName}`)" :alt="topic.title">
        </div>

        <div class="text-container">
            <h1 :style="this.h1Style">{{topic.title}}</h1>
        </div>
        <info-card v-if="!isHidden" transition="expand" :details="topic['infoCard']" id="info" />
    </div>
</template>

<script>
import InfoCard from './InfoCard.vue'

import {eventBus} from '../main.js'

    export default {
        name: 'topic-banner',
        data() {
            return {
                isHidden: this.topic.detailHidden
            }
        },
        components: {
            "info-card": InfoCard
        },
        props:['topics', 'topic', 'infoCard'],
        computed: {
            divStyle() {
                return {"backgroundColor": this.topic.bgColour};
            },
            h1Style() {
                return {"color": this.topic.titleColour};
            },
            icon_heading_flip() {
                if(this.topic.flip == true) {
                  return {"flex-direction": "row-reverse"};  
                }
            }
        },
        methods: {
            handleClick() {
                this.isHidden = !this.isHidden;
                eventBus.$emit('topic-selected', this.topic);
                console.log("Hidden Data on Click:", this.isHidden)
            }
        },
        mounted() {
        console.log("When loaded hidden is: ", this.isHidden)
        // console.log("When loaded infoCard is: ", this.infoCard)
        console.log("When loaded topic is: ", this.topic)
        console.log("When loaded topics is: ", this.topics)
    }
}
</script>

<style lang="css" scoped>
.main {
    display: inline-flex;
    align-items: center;
    width: 100vw;
    max-width: 100%;
    transition-duration: 0.5s;
    opacity: 0.8;
    flex-wrap: wrap;
}
.main:hover {
    opacity: 1;
}
@media screen and (max-width: 900px) {
 .main{
    flex-direction: column-reverse;
    flex-wrap: wrap;
    padding: 1em 0;
  }
}
.img-container, .text-container {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 50%;
    height: auto;
    margin: 0;
    padding: 0;
}
h1 {
    font-size: 12vh;
}
img {
    max-height: 200px;
    max-width: 200px;
}
</style>