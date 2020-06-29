<template>
    <div v-on:click="[handleClick()]" :style="[this.divStyle]" :topic="topic" class="main">

        <div class="img-container">
            <img :src="require(`@/assets/icons/${topic.imgName}`)" :alt="topic.title">
        </div>

        <div class="text-container">
            <h1 :style="this.h1Style">{{topic.title}}</h1>
        </div>
        <!-- <info-card v-if="!isHidden" transition="expand" :details="topic['infoCard']" id="info" /> -->
    </div>
</template>

<script>
// import InfoCard from './InfoCard.vue'

import {eventBus} from '../main.js'

    export default {
        name: 'topic-banner',
        data() {
            return {
                isHidden: true
            }
        },
        components: {
            // "info-card": InfoCard
        },
        props:['topics', 'topic'],
        computed: {
            divStyle() {
                return {"backgroundColor": this.topic.bgColour};
            },
            h1Style() {
                return {"color": this.topic.titleColour};
            }
            // ,
            // icon_heading_flip() {
            //     if(this.topic.flip == true) {
            //       return {"flex-direction": "row-reverse"};  
            //     }
            // }
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
    /* border: rebeccapurple solid ; */
}
.main {
    border-radius: 0.4em;
    margin: 1em;
    min-height: 40vh;
    min-width: 25vw;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    /* display: inline-flex;
    justify-content: center;
    /* align-items: center; */
    /* width: 30vw;
    max-width: 30vw;
    transition-duration: 0.5s;
    opacity: 1;
    flex-wrap: wrap;
    
    flex-direction: column; */ 
}
.main:hover {
    opacity: 0.8;
}
.img-container, .text-container {
    display: flex;
    justify-content: center;
    align-items: center;
}
.img-container {
    height: 250px;
}

h1 {
    font-size: 6vh;
}
img {
    max-height: 200px;
    max-width: 200px;
}
</style>