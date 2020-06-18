<template>
        <div v-on:click="[hidden = !hidden, handleClick()]" :style="[this.divStyle, this.icon_heading_flip]" :topic="topic" class="main">

                <div class="img-container">
                    <img :src="require(`@/assets/icons/${topic.imgName}`)" :alt="topic.title">
                </div>

                <div class="text-container">
                    <h1 :style="this.h1Style">{{topic.title}}</h1>
                </div>

                <!-- <info-card v-if="infoCard != null" :details="infoCard" :hidden="hidden" style="display: none" id="info" /> -->

        </div>
</template>

<script>
import InfoCard from './InfoCard.vue'

import {eventBus} from '../main.js'

    export default {
        name: 'topic-banner',
        data() {
            return {
                hidden: true,
                info: null
            }
        },
        components: {
            "info-card": InfoCard
        },
        props:['topic', 'infoCard'],
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
        watch:{
            hidden: function (value, oldValue) { 
                if(this.hidden){
                    return document.getElementById("info").style.display = "none";
                } else {
                    return document.getElementById("info").style.display = null;
                }
            }
        },
        methods: {
            handleClick() {
                eventBus.$emit('topic-selected', this.topic);
            }
        }
    }
</script>

<style lang="css" scoped>
.main {
    display: inline-flex;
    align-items: center;
    flex-wrap: wrap;
    width: 100vw;
    max-height: 20%;
    transition-duration: 0.5s;
}
.main:hover {
    opacity: 0.8;
}
.img-container, .text-container {
    display: flex;
    align-items: center;
    justify-content: center;
    min-width: 50%;
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
/* .info {
    transition-duration: 5s;
    transition:cubic-bezier(0.075, 0.82, 0.165, 1);
} */
</style>