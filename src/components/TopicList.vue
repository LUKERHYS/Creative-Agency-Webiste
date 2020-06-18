<template>
    <div>
        <topic-banner v-for="(topic, index) in topics" :topic="topic" :infoCard="infoCard" :key="index" id="" />
    </div>

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
                isHidden: false
                }
        },
        mounted() {
            eventBus.$on('topic-selected', (topic) => {
            this.infoCard = topic;
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