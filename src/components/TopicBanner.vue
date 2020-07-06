<template>
    <div v-on:click="handleClick()" :style="[this.divStyle, this.icon_heading_flip]" :topic="topic" class="main">

        <div class="img-container">
            <img :src="require(`@/assets/icons/${topic.imgName}`)" :alt="topic.title">
        </div>

        <div class="text-container">
            <!-- <h1 :style="this.h1Style">{{topic.title}}</h1> -->
            <div class="description">
                <h1>{{topic.title}}</h1>
                <p>{{topic.blurb}}</p>
            </div>
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
                isHidden: true
            }
        },
        components: {
            "info-card": InfoCard
        },
        props:['topics', 'topic'],
        computed: {
            divStyle() {
                return {"backgroundColor": this.topic.bgColour};
            },
            h1Style() {
                return {"color": this.topic.titleColour};
            }
            ,
            icon_heading_flip() {
                if(this.topic.flip == true) {
                  return {"flex-direction": "row-reverse"};  
                }
            }
        },
        methods: {
            handleClick() {
                eventBus.$emit('hidden-state', this.isHidden = !this.isHidden);
                eventBus.$emit('topic-selected', this.topic);
            }
        }
    }
</script>

<style lang="css" scoped>
div {
    /* border: solid pink; */
}
#info {
  position: absolute;
  top: 0;
  left: 0;
}
.main {
    height: 900px;
    min-width: 17vw;
    display: flex;
    border-bottom: solid 0.5px #adadad;
    position: relative;
    /* box-shadow: 0.5em 0.5em 1em rgba(0, 0, 0, .4); */
}
.main:hover {
    /* opacity: 0.8; */
}
.main:active {
    /* box-shadow: 0.5em 0.5em 1em rgba(0, 0, 0, .0); */
}
.img-container, .text-container {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 50%;
    text-justify: left;
}
.text-container {
    flex-direction: column;
}
.title {
    padding: 0%;
    margin: 0%;
}
.description {
    max-width: 45%;
    padding: 0%;
    margin: 0%;
}
h1 {
    font-size: 10vh;
    color: #404040;
}
p {
    font-size: 2.5vh;
    color: #404040;
}
img {
    max-height: 45%;
    max-width: 45%;
}
</style>