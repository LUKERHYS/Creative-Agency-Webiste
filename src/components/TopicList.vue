<template>
    <ul>
        <topic-banner v-for="(topic, index) in topics" :topic="topic" :key="index" :style="flexListOrdering" />
        <info-card v-if="selectedTopic" :topic="selectedTopic" :style="flexListOrdering"/>
    </ul>
</template>

<script>
import TopicBanner from './TopicBanner.vue'
import InfoCard from './InfoCard.vue'

import {eventBus} from '../main.js'

    export default {
        name: 'topic-list',
        props: ['topics', 'topic'],
        components: {
            "topic-banner": TopicBanner,
            "info-card": InfoCard
        },
        data: function(){
            return {
                selectedTopic: null
            }
        },
        mounted() {
            eventBus.$on('topic-selected', (topic) => {
            this.selectedTopic = topic;
           })
        },
        computed: {
            flexListOrdering() {
                return {"order": this.index};
            }
        }
    }
</script>

<style lang="css" scoped>
ul {
    margin: 0px;
    padding: 0px;
    display: flexbox;
}
li {
    margin: 0px;
    padding: 0px;
}
</style>