<template>
    <ul>
            <topic-banner :topic="topic" :key="index" v-for="(topic, index) in topics" />
            <info-card v-if="selectedTopic" :topic="selectedTopic" :style="listOrder" />
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
            this.selectedTopic = this.topic;
           })
        },
        computed: {
            listOrder() {
                return {"order": this.topic.id};
            }
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