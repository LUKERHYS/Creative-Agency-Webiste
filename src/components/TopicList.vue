<template>
    <div>
        <topic-banner v-for="(topic, index) in topics" :topics="topics" :topic="topic" :key="index" id="" />
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