<template>
    <ul>
            <topic-banner v-for="(topic, index) in topics" :topic="topic" :infoCard="infoCard" :key="index" />
            <info-card v-if="infoCard" :details="this.infoCard" style="display: none" id="info" :style="this.divPosition"/>
    </ul>
</template>

<script>
import TopicBanner from './TopicBanner.vue'
import InfoCard from './InfoCard.vue'

import {eventBus} from '../main.js'

    export default {
        name: 'topic-list',
        props: ['topics'],
        components: {
            "topic-banner": TopicBanner,
            "info-card": InfoCard
        },
        data: function(){
            return {
                infoCard: null,
                listOrder: null
            }
        },
        computed: {
            divPosition() {
                return {"order": this.listOrder};
            }
        },
        mounted() {
            eventBus.$on('topic-selected', (topic) => {
            this.infoCard = topic;
            this.listOrder = topic.id;
            console.log("LIST_ORDER: ", this.listOrder);
           })
        }
    }
</script>

<style lang="css" scoped>
ul {
    margin: 0px;
    padding: 0px;
    display: flex;
    flex-direction: column;
}
li {
    margin: 0px;
    padding: 0px;
}
</style>