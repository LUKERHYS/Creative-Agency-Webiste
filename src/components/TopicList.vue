<template>
    <div class="topic-container">
        <topic-banner class="topic" v-for="(topic, index) in topics" :topics="topics" :topic="topic" :key="index" id="" />
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
            "topic-banner": TopicBanner
        },
        data: function(){
            return {
                isHidden: false
            }
        }
    }
</script>

<style lang="css" scoped>
.topic-container {
    display: flex;
    max-width: 100vw;
    align-items: flex-start;
    justify-content: center;
}
.topic {
    max-width: 90vw;
}
</style>